<template>
    <div class="card">
        <div class="card-img">
            <img :src="objComic.thumb" :alt="objComic.series">
        </div>
        <div class="card-txt">
            <div class="caps">{{objComic.series}}</div>
            <div class="sub">{{objComic.type}}</div>
        </div>
        <div class="details">
           <span>{{objComic.price}}</span>
        </div>
    </div>
</template>

<script>
    export default {
        name:'ComicCard',
        props:[
            'objComic',
        ]
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables.scss' as *;
@use '../assets/styles/partials/mixin.scss' as *;
.card{
    cursor: pointer;
    position: relative;
    width: calc(100% / 6);
    padding: .5rem;
    @include my-flex-col;
    align-items: flex-start;
    color: $white;
    .details{
        position: absolute;
        top: 0.5rem;
        left: 0.5rem;
        width: 170px;
        height: 170px;
        font-weight: 900;
        display: none;
        span{
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
    }
    .card-img{
        width: 170px;
        height: 170px;
        overflow: hidden;
        img{
            max-width: 100%;
        }
        
    }
    .card-txt{
        width: fit-content;
        max-width: calc(100% - 1rem);
        .sub{
            text-transform: capitalize;
            color: $dark;
            font-size: 85%;
        }
        
    }
    &:hover{
        .details{
            display: block;
            background-color: $layover;
        }
        .sub{
            color: $white;
        }
    }
}

</style>