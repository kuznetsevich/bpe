<template>
  <v-layout class="d-flex mt-8 justify-center">
    <AppPrivacy />
  </v-layout>
</template>

<script>
import AppPrivacy from './Dialogs/AppPrivacy';

export default {
  name: 'AppFooter',
  components: { AppPrivacy },
  data (){
    return {
      //
    };
  }
};

</script>

<style scoped>

</style>