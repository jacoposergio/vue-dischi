<template>
   <div class="choose-genre">
                <label for="cars">Filtra album per genere</label>
                     <select name="genre" id="genre">
                         <option value="tutti">Tutti</option>
                         <option value="rock">Rock</option>
                         <option value="pop">Pop</option>
                         <option value="jazz">Jazz</option>
                         <option value="metal">Metal</option>
                     </select>
            </div>
</template>

<script>
export default {
    name: "FilterComponent",
    data(){
        return{
           url: "https://flynn.boolean.careers/exercises/api/array/music",
           genres:[],
           filter: "",
        }
    }


}

</script>

<style lang="scss" scoped>
@import'@/assets/scss/vars.scss';

</style>