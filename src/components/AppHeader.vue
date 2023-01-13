<script>
    name: 'AppHeader'
    export default {
        data(){ 
            return{
                logo: '../public/img/dc-logo.png',
                itemActive: null,
                nav: [
                    
                    'CHARACTERS',                        
                    'COMICS',                              
                    'MOVIES',                              
                    'TV',                              
                    'GAMES',                              
                    'COLLECTIBLES',                              
                    'VIDEOS',                              
                    'FANS',                              
                    'NEWS',                              
                    'SHOP',               

                ]
            }
        },
        //metodo per settare l'itemActive uguale all'index dell'elemento cliccato
        methods: {
            liActive(index){    
                this.itemActive = index
            }
        },
        
    }
</script>

<template>
    <header class="h-100-px">
        <div class="main-container">
            <div class="row">
                <!-- LOGO  -->
                <div class="logo-container">
                    <img :src="logo" alt="dc-logo">
                </div>
                <!-- NAVBAR  -->
                <nav>
                    <ul>
                        <!-- v-for per generare le voci dei menu  -->  <!-- se index è = a iteamActive, aggiungo la classe 'active'--> <!--invoco la funzione al click-->
                        <li v-for="(item,index) in nav" :key="index" :class="(index === itemActive ) ? 'active' : ''" @click="liActive(index)">
                            <span>{{ item }}</span>
                        </li>
                    </ul>
                </nav>
            </div>
        </div>
    </header>
</template>

<style lang="scss">
  @use './styles/partials/_variables.scss' as *;
  @use './styles/partials/_mixins.scss' as *;

    header *:not(span){
        height: 100%;
    }

    .row{
        
        .logo-container{
            padding: 1rem;
        }

        nav ul{
            @include flex-between;
            font-size: .8rem;
            font-weight: 600;

            li:not(:last-child){
                margin-right: 1.5rem;
            }

            li{
                &:hover{
                    cursor: pointer;
                    color: $brand-primary;
                    border-bottom: 3px solid $brand-primary;
                }

                &.active{
                    color: $brand-primary;
                    border-bottom: 3px solid $brand-primary;
                }
    
                span{
                    line-height: 100px;
                }
            }
        }       
    }

</style>