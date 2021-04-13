<template>
  <VApp>
    <AppPreloader />
    <VContainer class="container-custom-main">
      <AppIndex />
      <AppFooter />
    </VContainer>
  </VApp>
</template>

<script>

import AppPreloader from './components/Loaders/AppPreloader';
import AppIndex from '@/components/AppIndex';
import AppFooter from '@/components/AppFooter';
export default {
    name: 'App',
    components: { AppIndex, AppFooter },
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