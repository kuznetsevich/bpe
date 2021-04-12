<template>
  <div class="preloader">
    <div class="cube"></div>
    <div class="cube"></div>
    <div class="cube"></div>
    <div class="cube"></div>
  </div>
</template>

<script>
export default {
  name: 'AppPreloader'
};
</script>

<style>
 .preloader {
   display: flex;
   justify-content: center;
   align-items: center;
   position: fixed;
   top: 0;
   left: 0;
   width: 100vw;
   height: 100vw;
   background-color: lightgray;
   z-index: 999;
 }

</style>