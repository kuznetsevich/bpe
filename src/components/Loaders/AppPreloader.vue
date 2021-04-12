<template>
  <transition name="fade">
    <div class="preloader">
      <div class="spin">
        <p>Processing data ...</p>
      </div>
    </div>

  </transition>
</template>

<script>
export default {
  name: 'AppPreloader'
};
</script>

<style scoped>
 .preloader {
   display: flex;
   flex-direction: column;
   align-items: center;
   justify-content: center;
   position: absolute;
   width: 100%;
   height: 100%;
   z-index: inherit;
 }
</style>