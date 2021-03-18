<template>
  <div>
    <VCard
      class="mx-auto"
      outlined
    >
      <VToolbar
        flat
        color="green darken-2"
      >
        <VIcon>mdi-account</VIcon>
        <VToolbarTitle class="font-weight-light">
          User Profile
        </VToolbarTitle>
        <VSpacer />
        <VBtn
          color="green darken-4"
          fab
          small
          @click="isEditing = !isEditing"
        >
          <VIcon v-if="isEditing">
            mdi-close
          </VIcon>
          <VIcon v-else>
            mdi-pencil
          </VIcon>
        </VBtn>
      </VToolbar>

      <VListItem three-line>
        <VListItemContent>
          <VRow>
            <VCol
              cols="12"
              md="4"
            >
              <VTextField
                v-model="firstName"
                :disabled="!isEditing"
                label="First name"
                required
              />
            </VCol>
            <VCol
              cols="12"
              md="4"
            >
              <VTextField
                v-model="lastName"
                :disabled="!isEditing"
                label="Last name"
                required
              />
            </VCol>
            <VCol
              cols="12"
              md="4"
            />
          </VRow>
        </VListItemContent>
      </VListItem>

      <VCardActions>
        <VSpacer />
        <VBtn
          :disabled="!formValid()"
          color="success"
          large
          @click="updateUser"
        >
          {{ $t('update') }}
        </VBtn>
      </VCardActions>
    </VCard>
    <VCard
      class="mx-auto pass_change"
      dark
    >
      <VToolbar flat>
        <VIcon>mdi-key-variant</VIcon>
        <VToolbarTitle class="font-weight-light">
          Update password
        </VToolbarTitle>
        <VSpacer />
        <VBtn
          color="#385F73 darken-4"
          fab
          small
          @click="changePass = !changePass"
        >
          <VIcon v-if="changePass">
            mdi-close
          </VIcon>
          <VIcon v-else>
            mdi-pencil
          </VIcon>
        </VBtn>
      </VToolbar>

      <VListItem
        v-if="changePass"
        three-line
      >
        <VListItemContent>
          <VRow>
            <VCol
              cols="12"
              md="12"
            >
              <VTextField
                v-model="oldPass"
                :disabled="pending"
                label="Current password"
                required
              />
            </VCol>
            <VCol
              cols="12"
              md="12"
            >
              <VTextField
                v-model="newPass"
                :disabled="pending"
                label="New password"
                required
              />
            </VCol>
            <VCol
              cols="12"
              md="12"
            >
              <VTextField
                v-model="reTypeNewPass"
                :disabled="pending"
                label="ReType new password"
                required
              />
            </VCol>
          </VRow>
        </VListItemContent>
      </VListItem>

      <VCardActions v-if="changePass">
        <VSpacer />
        <VBtn
          :disabled="!formPassValid()"
          color="success"
          large
          @click="updatePass"
        >
          {{ $t('update_password') }}
        </VBtn>
      </VCardActions>
    </VCard>
  </div>
</template>

<script>
export default {
    name: 'AppProfile',
    data () {
        return {
            pending: false,
            firstName: '',
            lastName: '',
            isEditing: false,
            changePass: false,

            oldPass: '',
            newPass: '',
            reTypeNewPass: '',
        };
    },
    created () {
        this.loadAll();
    },
    methods: {
        formPassValid () {
            return !this.pending && this.oldPass.length > 0 && this.newPass.length > 0 && this.newPass === this.reTypeNewPass;
        },

        formValid () {
            return this.isEditing && this.firstName.length > 0 && this.lastName.length > 0;
        },

        loadAll () {
            this.pending = true;
            this.askBackend('data/profile', {}).then(
                data => {
                    this.pending = false;
                    if (data.ok) {
                        this.firstName = data.user.first_name;
                        this.lastName = data.user.last_name;
                    }
                },
                e => console.error(e),
            );
        },

        updatePass () {
            this.pending = true;
            this.askBackend('data/profile/update_password', {
                old_pass: this.oldPass,
                new_pass: this.newPass
            }).then(
                data => {
                    this.pending = false;
                    !data.ok ? this.showError(data.error):this.showOk('Password changed');
                },
                e => console.error(e),
            );
        },

        updateUser () {
            this.pending = true;
            this.askBackend('data/profile/update', {
                first_name: this.firstName,
                last_name: this.lastName,
            }).then(
                data => {
                    this.pending = false;
                    if (data.ok) {
                        this.firstName = data.user.first_name;
                        this.lastName = data.user.last_name;
                    }
                },
                e => console.error(e),
            );
        },
    }
};
</script>

<style scoped>
  .pass_change {
    margin-top: 20px;
  }
</style>