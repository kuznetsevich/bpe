<template>
 <v-app>
   <v-container class="container-custom-main">
     <AppNavigation />
     <AppGenerator />
   </v-container>
 </v-app>
</template>

<script>

  import AppNavigation from '@/components/AppNavigation'
  import AppGenerator from "@/components/AppGenerator";
  export default {
    name: "App",
    components: {AppGenerator, AppNavigation },
    data (){
      return {
        //
      }
    }
  }


</script>

<style style scoped lang="scss">

.container-custom-main {
  padding: 30px;
  max-width: 934px;
}

</style>