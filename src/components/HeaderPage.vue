<template>
  <header>
    <div class="spotify-logo">
        <img src="../assets/Spotify_logo_without_text.svg.png" alt="spotify logo">
    </div>
  </header>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@import'@/assets/scss/vars.scss';

    header{
        height: 50px;
        background-color: $bg_first_color;
        color: white;

        .spotify-logo{

          img{
            height: 30px;
            padding: 0 1.5rem;
            margin-top: 10px;
          }
        }
        
    }

</style>
