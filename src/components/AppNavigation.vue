<template>
 <nav>
   <v-tabs :width="width" background-color="transparent" class="navi-tabs">
     <v-tab>Generator</v-tab>
     <v-tab>Settings</v-tab>
     <v-tab>Instruction</v-tab>
     <v-tab>Other apps</v-tab>
   </v-tabs>
 </nav>
</template>

<script>

export default {
  name: "AppNavigation",
  computed: {
    width () {
      switch (this.$vuetify.breakpoint.name) {
        case 'xs': return 220
        case 'sm': return 400
        case 'md': return 500
        case 'lg': return 600
        case 'xl': return 800
      }
    },
  },
}

</script>

<style scoped lang="sass">
  .navi-tabs{
    margin-bottom: 30px;
    letter-spacing: normal;
  }
</style>