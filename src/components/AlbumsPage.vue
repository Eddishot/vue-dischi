<template>
    <div class="bg-color">
        <div class="container">
            <GenreSearch
                @typeOfGenre="albumFilter">
            </GenreSearch>
            <div class="row row-cols-5">
                <div class=" col mb-2" v-for="(album, i) in filteredAlbums" :key="i">
                    <SingleAlbum   
                        :title="album.title"
                        :author="album.author"
                        :poster="album.poster"
                        :year="album.year"
                        :genre="album.genre">
                      
                    </SingleAlbum>
                </div>

            </div>
        </div>

    </div>
</template>

 <script>
    import SingleAlbum from "./SingleAlbum.vue"
    import axios from "axios";
    import GenreSearch from "./GenreSearch.vue";
 export default {  
        name:"AlbumsPage",

        components:{

         SingleAlbum,
          GenreSearch,

        },

        data(){ return{
                arrayAlbum: [],
                searchByGenre:"",
            }
        },
                
               
        

        methods:{

            albumFilter(genre){
                this.searchByGenre = genre;

            },

            albumByGenre(){
                this.searchByGenre="";
            }

        },

        computed:{
            filteredAlbums(){
                if(!this.searchByGenre){
                    return this.arrayAlbum;
                }
                return this.arrayAlbum.filter((disc) =>{
                    return this.searchByGenre.toLowerCase()=== disc.genre.toLowerCase()
                })
            }
        },
        
        
        mounted(){
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((resp)=>{
                this.arrayAlbum.push(...resp.data.response)
        })
    }
   }

           
 </script>

 <style lang="scss" >
    @import "~bootstrap/scss/bootstrap";

 .bg-color{
     background-color: #192d3b;
     padding: 20px;
 }
 </style>

       
