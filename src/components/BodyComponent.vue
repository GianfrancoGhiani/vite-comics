<template>
    <!-- main body divided inot 2 pts -->
    <section><!-- temporary empty sect --></section>
    <!-- blue bg section -->
    <section class="blue-pt">
        <div class="container">
            <div class="merch" v-for="(item, index) in shop" :key="index">
                <img :src="getPath(item)" :alt="shop.name">
                <div>{{item.name}}</div>
            </div>
        </div>
    </section>
</template>

<script>
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
                    
                ]
            }
        },
        methods: {
            getPath(shop){
                return new URL(shop.path, import.meta.url).href;
            },
        },
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables.scss' as *;
@use '../assets/styles/partials/mixin.scss' as *;
@use '../assets/styles/general.scss' as *;
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
                text-transform: uppercase;
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