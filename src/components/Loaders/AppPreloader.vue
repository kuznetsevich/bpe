<template>
    <div class="preloader">
      <div class="loader"></div>
      <div class="loader_text">{{percent}}%. {{notes}}</div>
    </div>
</template>

<script>
export default {
  name: 'Preloader'

};


</script>

<style lang="scss" scoped>

 .preloader {
   display: flex;
   flex-direction: column;
   justify-content: center;
   align-items: center;
   position: fixed;
   top: 0;
   left: 0;
   width: 100vw;
   height: 100vh;
   background-color: white;
   z-index: 9999;

   .loader {
     width: 48px;
     height: 48px;
     border-radius: 50%;
     display: block;
     margin:15px auto;
     position: relative;
     box-sizing: border-box;
     animation: rotation 2s linear infinite;
   }
   .loader::after,
   .loader::before {
     content: '';
     box-sizing: border-box;
     position: absolute;
     left: 0;
     top: 0;
     background: #FF3D00;
     width: 20px;
     height: 20px;
     transform: translate(-50%, 50%);
     border-radius: 50%;
   }
   .loader::before {
     left: auto;
     right: 0;
     background: #1d05d6;
     transform: translate(50%, 100%);
   }

   @keyframes rotation {
     0% {
       transform: rotate(0deg);
     }
     100% {
       transform: rotate(360deg);
     }
   }

    p {
      font-family: Roboto, Montserrat;
      font-weight: 400;
      font-size: 21px;
      margin-top: 40px;
    }
 }

</style>