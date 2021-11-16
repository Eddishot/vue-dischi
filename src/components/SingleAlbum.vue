<template>
    <div class="card p-2">
        <img :src="poster" class="card-img-top" alt="logo poster album">
        <div class="text-center card-body">
            <h4 class="card-title">{{title}}</h4>
            <h6 class="card-text">{{author}}</h6>
            <h6 class="card-text">{{year}}</h6>
        </div>
    </div>
</template>

<script >

export default {
    name:"SingleAlbum",
    props:{
        title: String,
        author: String,
        poster: String,
        year: String,
        genre: String,
    },
}
</script>

<style  lang="scss"scoped>
    .card{
        color:white ;
        height: 100%;
        background-color: #2b3a49 !important;
        img{
            height: 190px;
        }
        .card-title{
            color: white;
            margin-bottom: 15px;
        }


    }
</style>