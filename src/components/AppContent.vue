<script>
    name: 'AppContent'
    // importo la CardComic da inserire nel template 
    import CardComic from './items/CardComic.vue';
    // importo l'array dei comics dal file js 
    import comicsArray from '../assets/data/ArrayComicsData.js'
    export default {
        components:{
            CardComic
        },
        data(){
            return{
                // assegno il valore dell'array importanto alla chiave 'comics'
                comics: comicsArray
            }
        }
    }
</script>

<template>
    <section>
        <div id="jumbotron"></div>
        <div class="main-container">
            <div class="upper-title blue-label">
                <h2>CURRENT SERIES</h2>
            </div>
            <div class="row">
                <!-- ciclo la componente 'CardComic' per il numero degli oggetti contenuti nell'array comics, e definisco l'oggetto nella props 'comic' che passerò alla CardComic -->
                <CardComic v-for="(item,index) in comics" :comic="item" :key="index" />    
            </div>
            <div class="load blue-label">
                <h6>LOAD MORE</h6>
            </div>
        </div>
    </section>
</template>

<style lang="scss">
    @use './styles/partials/_variables.scss' as *;

    section{
        background-color: rgb(28,28,28);
        padding-bottom: 1rem;

        #jumbotron{
            background-image: url('/public/img/jumbotron.jpg');
            height: 37vh;
            background-size: cover;
        }

        .upper-title{
            display: inline-block;
            height: 2.5rem;
            padding: .25rem 1.25rem ;
            position: relative;
            bottom: 1.25rem;
        }

        .row{
            flex-wrap: wrap;
            padding: .5rem;
        }

        .load{
            display: inline-block;
            padding: .5rem 3rem;
            position: relative;
            left: 50%;
            transform: translate(-50%);
        }
    }
    
</style>