<script>
    name: 'AppHeader'
    export default {
        data(){ 
            return{
                logo: '../public/img/dc-logo.png'
            }
        }
        
    }
</script>
<template>
    <header class="h-100-px debug">
        <div class="main-container h-100">
            <div class="row h-100">
                <div class="logo-container">
                    <img :src="logo" alt="dc-logo" class="h-100">
                </div>
                <div>ciaoo</div>
            </div>
        </div>
    </header>
</template>
<style lang="scss">
  @use './styles/generals.scss' as *;
  @use './styles/partials/_variables.scss' as *;
  @use './styles/partials/_mixins.scss' as *;

    
    .row{
        @include flex-between;
        padding: 1rem;

        
    }
</style>