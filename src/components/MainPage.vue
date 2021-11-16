<template>
<div>
        <div class="logo-bar">
        <img src="../assets/logo-spotify.png" alt="logo spotify">
    </div>

    <AlbumsPage></AlbumsPage>
</div>

</template>

<script>
import AlbumsPage from "./AlbumsPage.vue"
export default{
    name:"MainPage",

    components:{
        AlbumsPage,
    }
    
}

</script>

<style lang="scss" scoped>

    .logo-bar{
        background-color:#2b3a46 ;
        padding: 10px;

        img{
            width: 55px;
            margin-left: 8px;
        }
    }

</style>