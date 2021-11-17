<template>
  <div>
      <div class="input-group mx-auto" style="max-width:400px">
          <select class="form-control fs-2" placeholder="Cerca il tuo genere musicale"
          v-model="searchByGenre" @change="$emit(`typeOfGenre`, searchByGenre )">
              <option value="">All genre</option>
              <option value="rock">rock</option>
              <option value="metal">metal</option>
              <option value="pop">pop</option>
              <option value="jazz">jazz</option>
              
          </select>
           
            <!-- <button type="button" class="btn btn-outline-primary" @click=" typeOfGenreSearch">Cerca</button> -->
        </div>
  </div>
</template>

<script>
export default {
    name:"GenreSearch",
    data(){
        return{
            searchByGenre:"",
        }
    },

    // methods:{
    //     typeOfGenreSearch(){
    //         this.$emit(" typeOfGenre", this.searchByGenre);
    //     }
    // }

}
</script>

<style>

</style>