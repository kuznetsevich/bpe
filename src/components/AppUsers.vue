<template>
  <VRow no-gutters>
    <VCol
      cols="12"
      sm="12"
    >
      <VCard>
        <VCardTitle>
          <VTextField
            v-model="search"
            append-icon="mdi-magnify"
            label="Поиск"
            single-line
            hide-details
          />
        </VCardTitle>
        <VDataTable
          :loading="pending"
          :headers="headers"
          :items="users"
          :search="search"
        >
          <template v-slot:item.rights="{ item }">
            <VChip
              v-for="r in item.rights"
              class="role_chip"
              :color="getRoleColor(r)"
              dark
            >
              {{ getRoleText(r) }}
            </VChip>
          </template>
          <template v-slot:item.active="{ item }">
            <VSimpleCheckbox
              v-model="item.active"
              disabled
            />
          </template>
          <template v-slot:top>
            <VToolbar flat>
              <VDialog
                v-model="dialog"
                max-width="500px"
              >
                <VCard>
                  <VCardTitle>
                    <span class="headline">
                      {{ formTitle }}
                    </span>
                  </VCardTitle>

                  <VCardText>
                    <VContainer>
                      <VRow>
                        <VCol
                          cols="12"
                          sm="6"
                        >
                          <VTextField
                            v-model="editedItem.email"
                            :disabled="pending"
                            label="Email"
                          />
                        </VCol>
                        <VCol
                          cols="12"
                          sm="6"
                        >
                          <VCheckbox
                            v-model="editedItem.active"
                            label="User active"
                            :disabled="pending"
                          />
                        </VCol>
                        <VCol
                          cols="12"
                          sm="6"
                        >
                          <VTextField
                            v-model="editedItem.first_name"
                            :disabled="pending"
                            label="First name"
                          />
                        </VCol>
                        <VCol
                          cols="12"
                          sm="6"
                        >
                          <VTextField
                            v-model="editedItem.last_name"
                            label="Last name"
                            :disabled="pending"
                          />
                        </VCol>
                      </VRow>
                    </VContainer>
                  </VCardText>
                  <VCardActions>
                    <VSpacer />
                    <VBtn
                      color="blue darken-1"
                      :disabled="pending"
                      text
                      @click="close"
                    >
                      Cancel
                    </VBtn>
                    <VBtn
                      color="blue darken-1"
                      :disabled="!updateValid()"
                      text
                      @click="save"
                    >
                      Save
                    </VBtn>
                  </VCardActions>
                </VCard>
              </VDialog>
            </VToolbar>
          </template>
          <template v-slot:item.actions="{ item }">
            <VIcon
              small
              class="mr-2"
              @click="editItem(item)"
            >
              mdi-pencil
            </VIcon>
          </template>
          <template v-slot:no-data>
            <VBtn
              color="primary"
              @click="initialize"
            >
              Reset
            </VBtn>
          </template>
        </VDataTable>
      </VCard>
    </VCol>
  </VRow>
</template>

<script>
export default {
    name: 'AppUsers',
    data () {
        return {
            dialog: false,
            dialogDelete: false,
            pending: false,
            search: '',
            headers: [
                { text: 'Active', align: 'start', value: 'active' },
                { text: 'First name', align: 'start', value: 'first_name' },
                { text: 'Last name', value: 'last_name' },
                { text: 'Email', value: 'email' },
                { text: 'Register data', value: 'register_date' },
                { text: 'Roles', value: 'rights' },
                { text: 'Actions', value: 'actions', sortable: false },
            ],
            users: [],
            editedIndex: -1,
            editedItem: {
                user_id: 0,
                email: '',
                first_name: '',
                last_name: '',
                active: false,
            },
            defaultItem: {
                user_id: 0,
                email: '',
                first_name: '',
                last_name: '',
                active: false,
            },
            formTitle: '',
            rightsMap: [],
        };
    },
    created () {
        this.loadAll();
        this.loadRights();
    },
    methods: {
        loadRights () {
            this.askBackend('data/users/roles/list', {}).then(
                data => {
                    if (data.ok) {
                        this.rightsMap = data.rights;
                    }
                },
                err => {
                    console.error(err);
                    this.showError('error load user rights');
                },
            );
        },
        loadAll () {
            this.pending = true;
            this.askBackend('data/users/list', {}).then(
                data => {
                    this.pending = false;
                    if (!data.ok) {
                        this.showError('Error load users');
                        return;
                    }
                    this.prepareUsers(data.persons, data.person_rights);
                },
                e => {
                    console.error(e);
                    this.showError('Error load users');
                }
            );
        },

        prepareUsers (userData, userRights) {
            userData.forEach(user => {
                user.rights = [];
                userRights.forEach(uRights => {
                    if (uRights.user_id !== user.user_id) {
                        return;
                    }
                    user.rights.push(uRights.right_id);
                });
            });
            this.users = userData;
        },

        getRoleColor (rId) {
            const name = this.rightsMap[+rId];
            switch (name) {
                case 'admin':
                    return 'red';
                case 'moderator':
                    return 'orange';
            }
            return 'green';
        },
        getRoleText (rId) {
            return this.rightsMap[+rId];
        },

        editItem (item) {
            this.editedIndex = this.users.indexOf(item);
            this.editedItem = Object.assign({}, item);
            this.formTitle = `Edit user: ${this.editedItem.email} - ${this.editedItem.user_id}`;
            this.dialog = true;
        },

        close () {
            this.dialog = false;
            this.$nextTick(() => {
                this.editedItem = Object.assign({}, this.defaultItem);
                this.editedIndex = -1;
            });
        },

        updateValid () {
            return !this.pending &&
          this.editedItem.email.length > 0 &&
          this.editedItem.first_name.length > 0 &&
          this.editedItem.last_name.length > 0;
        },

        save () {
            this.pending = true;
            this.askBackend('data/users/update', {
                user_id: this.editedItem.user_id,
                first_name: this.editedItem.first_name,
                last_name: this.editedItem.last_name,
                email: this.editedItem.email,
                active: this.editedItem.active,
            }).then(
                data => {
                    this.pending = false;
                    if (data.ok) {
                        this.showOk(data.msg);
                        this.close();
                        this.loadAll();
                    } else {
                        this.showError('error while update');
                    }
                },
                e => {
                    console.error(e);
                    this.showError('Error update user');
                }
            );
        },
    }
};
</script>

<style scoped>
  .role_chip {
    margin: 5px;
  }
</style>