<template>
  <main>
      <div v-if="isLoaded" class="main-wrapper">
          <div class="container-fluid">
               <FilterComponent/> 
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
import FilterComponent from './FilterComponent.vue';

export default {
   name: "MainPage",
    components: {
        SongCard,
        LoaderComponent,
        FilterComponent
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
    height: 100%;
    
    .main-wrapper{
        padding: 50px 0;
        margin: 0 auto;
        width: 70%;

     .choose-genre{
        display: flex;
        justify-content: center;
        margin-bottom: 2rem;

        label{
            color: white;
            margin-right: 1rem;
            font-size: 1.2rem;
        }

        option{
            font-family: $main_font;;
        }
     }
        .col{
            display: flex;
        }
    }

}

</style>
