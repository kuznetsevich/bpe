<template>
  <VApp>
    <VContainer class="container-custom-main">
      <AppPreloader />
      <!--<AppIndex />
      <AppFooter /> -->
    </VContainer>
  </VApp>
</template>

<script>

/*import AppIndex from '@/components/AppIndex';
import AppFooter from '@/components/AppFooter'; */
import AppPreloader from './components/Loaders/AppPreloader';
export default {
    name: 'App',
    components: { AppPreloader, AppIndex, AppFooter },
    data (){
        return {
        //
        };
    }
};



</script>

<style style scoped lang="scss">

.container-custom-main {
  max-width: 934px;
  padding-right: 3.2rem;
  padding-left: 3.2rem;
  padding-top: 1.6rem;
}

</style>