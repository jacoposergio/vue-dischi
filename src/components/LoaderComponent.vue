<template>
  <div class="loader">
     <div class="text">
        loading...
     </div>
  </div>
</template>

<script>
export default {
    name: "LoaderComponent",

}

</script>

<style lang="scss" scoped>
@import'@/assets/scss/vars.scss';

    .loader{
        position: fixed;
        top: 0;
        left: 0;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 100%;
        height: 100%;
        background-color: #fefefe;
         animation-name: pulse;
        animation-duration: 3s;
        animation-iteration-count: infinite;

 

        .text{
            text-transform: uppercase;
            letter-spacing: 2px;
        }
    }

           @keyframes pulse {
             0%   {transform: scale(1);}
            25%  {transform: scale(1.3);}
            50%  {transform: scale(1);}
            75%  {transform: scale(1.3);}
            100% {transform: scale(1);}       
        }

</style>