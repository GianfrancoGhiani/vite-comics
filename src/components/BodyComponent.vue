<template>
    <!-- main body divided into 3 pts -->
    <!-- jumbo -->
    <section class="jumbo">
        <JumbotronComponent />
    </section>
    <!-- comics list -->
    <section class="comic-list">
        <div class="container">
            <ComicCard v-for="(comic, index) in comicList" :key="index" :objComic="comic"/>
        </div>
        <button class="caps">load more</button>
    </section>
    <!-- blue bg section -->
    <section class="blue-pt">
        <div class="container">
            <div class="merch" v-for="(item, index) in shop" :key="index">
                <img :src="getPath(item)" :alt="shop.name">
                <div class="caps">{{item.name}}</div>
            </div>
        </div>
    </section>
</template>

<script>
import ComicCard from './ComicCard.vue';
import JumbotronComponent from './JumbotronComponent.vue'
import comicListData from '../assets/data/dc-comics.json';
    export default {
        name: 'BodyComponent',
        data() {
            return {
                shop:[
                    {
                        name: 'digital comics',
                        path: '../assets/img/buy-comics-digital-comics.png'
                    },
                    {
                        name: 'merch',
                        path: '../assets/img/buy-comics-merchandise.png'
                    },
                    {
                        name: 'subscription',
                        path: '../assets/img/buy-comics-subscriptions.png'
                    },
                    {
                        name: 'shop',
                        path: '../assets/img/buy-comics-shop-locator.png'
                    },
                    {
                        name: 'visa',
                        path: '../assets/img/buy-dc-power-visa.svg'
                    },
                    
                ],
                comicList: comicListData,
            }
        },
        components:{
            ComicCard,
            JumbotronComponent,
        },
        methods: {
            getPath(shop){
                return new URL(shop.path, import.meta.url).href;
            },
        },
        mounted() {
            
        },
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables.scss' as *;
@use '../assets/styles/partials/mixin.scss' as *;
.comic-list{
    background-color: $dark;
    padding: 3rem 0;
    @include my-flex-col;

    .container{
        @include my-flex-row;
        flex-flow: wrap;
        align-items: flex-start;
    }
    button{
        color: $white;
        background-color: $lightblue;
        padding: .8rem 3rem;
        width: fit-content;
        border: 0;
        font-weight: 700;
        cursor: pointer;
        &:hover{
            background-color: darken($color:  $lightblue, $amount: 10);
        }
    }
}

.blue-pt{
    background-color: $lightblue;
    height: 155px;
    @include my-flex-row;

    .container{
        @include my-flex-row;
        justify-content: space-around;
        padding: 0 1.5rem;
        .merch{
            width: calc(100% / 5);
            @include my-flex-row;
            justify-content: center;
            div{
                color: $white;
                
                margin-left: 1rem;
            }
            img{
                max-height: 4rem;
                max-width: 30%;
            }
            &:hover{
                cursor: pointer;
                div{
                    color: darken($color: $white, $amount: 15);
                }
                img{
                    filter: brightness(.85);
                }
            }
        }
    }
}
</style>