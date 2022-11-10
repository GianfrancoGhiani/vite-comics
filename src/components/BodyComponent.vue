<template>
    <!-- main body divided inot 2 pts -->
    <section><!-- temporary empty sect --></section>
    <!-- blue bg section -->
    <!-- problem: implementation of a dynamic img src -->
    <section class="blue-pt">
        <div class="container">
            <div class="merch">
                <img src="../assets/img/buy-comics-digital-comics.png" alt="digital comics">
                <div>digital comics</div>
            </div>
            <div class="merch">
                <img src="../assets/img/buy-comics-merchandise.png" alt="merch">
                <div>digital comics</div>
            </div>
            <div class="merch">
                <img src="../assets/img/buy-comics-subscriptions.png" alt="subscription">
                <div>digital comics</div>
            </div>
            <div class="merch">
                <img src="../assets/img/buy-comics-shop-locator.png" alt="shop">
                <div>digital comics</div>
            </div>
            <div class="merch">
                <img src="../assets/img/buy-dc-power-visa.svg" alt="visa">
                <div>digital comics</div>
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'BodyComponent',
        
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