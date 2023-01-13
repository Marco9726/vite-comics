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
        <div class="main-container">
            <div class="upper-title debug">
                <h2>CURRENT SERIES</h2>
            </div>
            <div class="row">
                <!-- ciclo la componente 'CardComic' per il numero degli oggetti contenuti nell'array comics, e definisco l'oggetto nella props 'comic' che passerò alla CardComic -->
                <CardComic v-for="(item,index) in comics" :comic="item" :key="index" >
                </CardComic>             
            </div>
        </div>
    </section>
</template>

<style lang="scss">

    section{
        background-color: rgb(28,28,28);

        .upper-title{
            width: 200px;
            text-align: center;
        }

        .row{
            flex-wrap: wrap;
            padding: .5rem;
        }
    }
    
</style>