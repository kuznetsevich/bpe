<template>
  <VApp>
    <VContainer class="container-custom-main">
      <AppIndex />
    </VContainer>
  </VApp>
</template>

<script>

import AppIndex from '@/components/AppIndex';
export default {
    name: 'App',
    components: { AppIndex },
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