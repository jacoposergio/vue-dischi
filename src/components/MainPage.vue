<template>
  <main>
      <div v-if="isLoaded" class="main-wrapper">
          <div class="container">
              <div class="row row-cols-md-5 row-cols-sm-3  ">
                  <div v-for="song, index in songList " class="col" :key="index" :element="song" >
                    <SongCard :info="song" />
                </div> 
            </div>
        </div>
    </div>
        <LoaderComponent v-else />
  </main>
</template>

<script>
import axios from "axios";
import SongCard from './SongCard.vue';
import LoaderComponent from './LoaderComponent.vue';

export default {
   name: "MainPage",
    components: {
        SongCard,
        LoaderComponent
    },
    
   data(){
       return{
           url: "https://flynn.boolean.careers/exercises/api/array/music",
           songList:[],
           isLoaded: false
       }
   },
     created() {
    this.getSongs();
   },

   methods:{
    getSongs(){
        axios.get(this.url).then( (result) =>{
            this.songList = result.data.response;
            this.isLoaded = true;
        })
        .catch((err)=>{
             console.log("Error",err);
        });
    }
   }
}
</script>


<style lang="scss" scoped>
@import'@/assets/scss/vars.scss';


main{
    background-color: $bg_second_color;
    height: 100vh;
    .main-wrapper{
        padding: 50px 0;
        margin: 0 auto;
        width: 70%;
    }

        .col{
            display: flex;
        }
}

</style>
