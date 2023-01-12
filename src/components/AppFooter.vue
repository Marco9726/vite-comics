<script>
    name: 'AppFooter'
    export default {
        data(){
            return{
                logo: '../public/img/dc-logo-bg.png',
                lists: [
                    {
                        title:'DC COMICS',
                        list: [
                            'Characters',
                            'Comics',
                            'Movies',
                            'TV',
                            'Games',
                            'Videos',
                            'News'
                        ]
                    },
                    {
                        title:'SHOP',
                        list: [
                            'Shop DC',
                            'Shop DC Collectibles'
                        ]
                    },
                    {
                        title:'DC',
                        list: [
                            'Terms Of Use',
                            'Privacy policy(New)',
                            'AD Choices',
                            'Advertising',
                            'Jobs',
                            'Subscriptions',
                            'Talent Workshops',
                            'CPSC Certificates',
                            'Rating',
                            'Shop Help',
                            'Contact Us'
                        ]
                    },
                    {
                        title:'SITES',
                        list: [
                            'DC',
                            'Mad Magazine',
                            'DC Kids',
                            'DC Universe',
                            'DC Power Visa'
                        ]
                    }
                ],
                socials: [
                    'footer-facebook.png',
                    'footer-periscope.png',
                    'footer-pinterest.png',
                    'footer-twitter.png',
                    'footer-youtube.png'
                ]
            }
        }
    }
</script>


<template>
    <footer>
        <!-- background container  -->
        <div id="background-container">
            <div class="main-container h-100">
                <div class="row h-100">
                    <div id="lists"> 
                        <!-- v-for per generare 4 ul  -->
                        <ul v-for="(item,index) in lists" :key="index">
                            <h4>{{ item.title }}</h4>
                            <!-- v-for per generare gli li delle varie liste  -->
                            <li v-for="(item,index) in lists[index].list" :key="index"> 
                                <a href="#">{{ item }}</a>

                            </li>
                        </ul>
                    </div>
                    <div id="logo-container">
                        <img :src="logo" alt="dc-logo" >
                    </div>
                </div>
            </div>

        </div>
        <!-- ultimo container scuro -->
        <div id="last-container" class="h-100-px">
            <div class="main-container h-100">
                <div class="row h-100">
                    <div id="sign-up">
                        <a href="#">
                            SIGN-UP NOW!
                        </a>
                    </div>
                    <ul>
                        <h4>FOLLOW US</h4>
                        <!-- v-for per genere le 5 immagini dei social -->
                        <li v-for="(item,index) in socials" :key="index">
                            <img :src="`/public/img/${item}`" alt="#">

                        </li>
                    </ul>
                </div>
            </div>
        </div>
        
    </footer>
</template>


<style lang="scss">
    @use './styles/partials/_variables.scss' as *;
    @use './styles/partials/_mixins.scss' as *;

    

    #background-container{
        background-image: url('../public/img/footer-bg.jpg');
        background-size: cover;
        height: 285px;
        overflow: hidden;
        .row{
            @include flex-between;

            #lists{
                display: flex;
                flex-direction: column;
                flex-wrap: wrap;
                padding-top: 2rem;

                ul{
                    margin-bottom: 1rem;
                    margin-right: 1rem;
                    h4{
                        color: white;
                        margin-bottom: .5rem;
                    }
                    
                    li{
                        line-height: .8rem;
                        
                        a{
                            color: $gray;
                            font-size: .65rem;
                            font-family: $mukta;
                            
                        }
                    }
                }
            }

            #logo-container{
                width: 45%;
                height: 100%;
                display: flex;
                align-items: center;

                img{
                    width: 100%;
                    vertical-align: 265px;
                }
            }
        }
    }

    #last-container{
        background-color: rgb(48,48,48);
        .row{
            align-items: center;

            #sign-up a{
                color: white;
                font-family: $mukta;
                border: 2px solid $brand-primary;
                padding: .3rem .5rem;
            }

            h4{
                color: $brand-primary;
            }

            ul{
                @include flex-between;
                align-items: center;
                li{
                    margin-left: 1rem;
                    img{
                        height: 1.75rem;
                    }
                    &:hover{
                        cursor: pointer;
                    }
                }
            }
        }
    }

</style>