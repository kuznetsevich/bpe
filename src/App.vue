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
  max-width: 934px;
  padding-right: 3.2rem;
  padding-left: 3.2rem;
  padding-top: 1.6rem;
}

</style>