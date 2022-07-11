<template>
  <div id="app">
      <HeaderPage/>
       <MainPage/>
       <SongCard/>
  </div>
</template>

<script>
import HeaderPage from './components/HeaderPage.vue'
import MainPage from './components/MainPage.vue'
import SongCard from './components/SongCard.vue'

export default {
  name: 'App',
  components: {
    HeaderPage,
    MainPage, 
    SongCard
   }
}
</script>

<style lang="scss">
@import'@/assets/scss/style.scss';



</style>
