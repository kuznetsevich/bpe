<template>
  <VContainer>
    <VRow no-gutters>
      <VCol
        cols="12"
        sm="12"
        md="4"
        lg="3"
      >
        <h1>Tasks</h1>
      </VCol>

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
            :items="bots"
            :search="search"
          />
        </VCard>
      </VCol>
    </VRow>
  </VContainer>
</template>

<script>
export default {
    name: 'AppHome',
    data () {
        return {
            search: '',
            pending: false,
            headers: [
                { text: 'Имя', align: 'start', value: 'first_name' },
                { text: 'Фамилия', value: 'last_name' },
                { text: 'Логин', value: 'login' },
                { text: 'Дата регистрации', value: 'register_date' },
            ],
            bots: [

            ]
        };
    },
    created () {
        this.loadAll();
    },
    methods: {
        loadAll () {
            this.pending = true;

        },
    }
};
</script>

<style scoped lang="scss">
    h1  {
        color: green;
    }

</style>