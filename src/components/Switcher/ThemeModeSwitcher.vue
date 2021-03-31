<template>
  <v-switch
      class="mt-0 pa-0"
      v-model="reverse"
      label="Dark mode"
  >
  </v-switch>
</template>

<script>
export default {
  name: 'ThemeModeSwitcher'
  themeButton.onclick = function() {
    page.classList.toggle('light-theme');
    page.classList.toggle('dark-theme');
  },
};
</script>

<style scoped>

</style>