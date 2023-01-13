<script>
    name: 'CardComic'
    export default {
        props:{
            comics : Array,
            // prop passata da AppContent
            comic: Object
        }
    }
</script>

<template >
    <div class="card">
        <div class="card-image">
            <!-- v-bind dell'attributo src nel quale inserisco la proprietà 'thumb' dell'oggetto comic  -->
            <img :src="comic.thumb" alt="">
        </div>
        <div class="card-label">
            <!-- prendo la proprietà 'series' dell'oggetto 'comic' -->
            {{ comic.series }}
        </div>
    </div>
</template>

<style lang="scss" scoped>
    @use './styles/partials/_variables.scss' as *;
    
    .card{
        width: calc(100% / 6 - 1rem);
        text-transform: uppercase;
        margin-bottom: 2rem;

        .card-image{
            width: 100%;
            height: calc(65vw / 6 - 1rem);
            overflow-y: hidden;
            margin-bottom: 1rem;

            img{
                width: 100%;
            }
        }
    }
</style>