<template>
  <div class="card">
    <div class="song-img">
        <img :src="info.poster" alt="">
    </div>
    <h3>{{info.title}}</h3>
    <h4>{{info.author}}</h4>
    <h5>{{info.year}}</h5>
</div>
</template>

<script>

export default {
    name: "SongCard",
    props: ['info']

//    data(){
//        return{
//            url: "https://flynn.boolean.careers/exercises/api/array/music",
//            songList:[],
//        }
//    },

//    created() {
//     this.getSongs();
//    },

//    methods:{
//     getSongs(){
//         axios.get(this.url).then( (result) =>{
//             this.songList = result.data.results
//         })
//         .catch((err)=>{
//              console.log("Error",err);
//         });
//     }
//    }

}
</script>

<style lang="scss" scoped>
@import'@/assets/scss/vars.scss';

.card{
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 1rem;
        background-color: $bg_first_color;
        text-align: center;
        margin-bottom: 1rem;

        .song-img{
            width: 100%;
            aspect-ratio: 1/1;
            background-color: black;
        }

        img{
            width:100% ;
        }

        h3{
            width: 100%;
            font-size: 1.5rem;
            padding: 0.5rem 0;
            margin-bottom: 0;
            color: white;
        }

        h4{
            width: 100%;
            font-size: 1.2rem;
            color: $subtext_color;
            margin-bottom: 0;
        }

        h5{
            width: 100%;
             font-size: 1rem;
            color: $subtext_color;
        }
    }

</style>
