<template>
    <div class="img-space">
        <div class="container">
            <h1 class="caps">current series</h1>
        </div>
    </div>
    
</template>

<script>
    export default {
        name:'JumbotronComponent',

    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables.scss' as *;
@use '../assets/styles/partials/mixin.scss' as *;
.img-space{
    background-image: url('../assets/img/jumbotron.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    height: 40vh;
    min-height: 250px;
    position: relative;
    .container{
        position: absolute;
        bottom: -1.8rem;
        left: 50%;
        transform: translate(-50%, 0);
    }
    h1{
        color: $white;
        background-color: $lightblue;
        padding: .8rem 2rem;
        width: fit-content;
        
    }
}
</style>