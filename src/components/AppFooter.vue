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
                ]
            }
        }
    }
</script>


<template>
    <footer>
        <div id="background-container">
            <div class="main-container h-100">
                <div class="row h-100">
                    <div id="lists">
                        <ul v-for="(item,index) in lists" :key="index">
                            <h4>{{ item.title }}</h4>
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
        <div id="last-container" class="h-100-px">
            <div class="main-container">
                
            </div>
        </div>
        
    </footer>
</template>


<style lang="scss" scoped>
    @use './styles/generals.scss' as *;
    @use './styles/partials/_variables.scss' as *;
    @use './styles/partials/_mixins.scss' as *;

    #background-container{
        background-image: url('../public/img/footer-bg.jpg');
        background-size: cover;
        height: 285px;
        .row{
            @include flex-between;

            #lists{
                @include flex-between;
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
                background-color: red;

                img{
                    width: 100%;
                    vertical-align: 265px;

                }
            }
        }
    }

    #last-container{

        background-color: rgb(48,48,48);
    
    }

</style>