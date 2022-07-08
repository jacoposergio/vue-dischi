<template>
  <main>
    <div class="main-wrapper">
        <div class="container">
            <div class="row row-cols-md-5 row-cols-sm-3  ">
                <div v-for="song, index in songList " class="col" :key="index" :productDetails="element" >
                    <SongCard/>
                </div> 
            </div>
        </div>
    </div>
  </main>
</template>

<script>
import SongCard from './SongCard.vue';

export default {
   name: "MainPage",
    components: {
        SongCard
    },
}
</script>


<style lang="scss" scoped>
@import'@/assets/scss/vars.scss';


main{
    .main-wrapper{
        margin: 50px auto;
        width: 70%;
    }
}

</style>
