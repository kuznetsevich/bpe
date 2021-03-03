<template>
 <nav>
   <v-tabs :width="width" background-color="transparent">
     <v-tab class="custom-transform-class text-none">Generator</v-tab>
     <v-tab class="custom-transform-class text-none">Settings</v-tab>
     <v-tab class="custom-transform-class text-none">Instruction</v-tab>
     <v-tab class="custom-transform-class text-none">Other apps</v-tab>
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
  .text-none{
    text-transform: capitalize
    }
</style>