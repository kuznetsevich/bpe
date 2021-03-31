<template>
  <v-switch
      class="mt-0 pa-0"
      @click="changeTheme"
      v-model="isBlacked"
      label="Dark mode"
  >
  </v-switch>
</template>

<script>
export default {
  name: 'ThemeModeSwitcher',
  data() {
    return {
      isBlacked: false,
      }
    },
  methods: {
    changeTheme() {
      this.$vuetify.theme.dark = this.isBlacked;
    }
  }
};
</script>

<style scoped>

</style>