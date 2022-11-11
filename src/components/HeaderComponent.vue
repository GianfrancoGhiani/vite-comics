<template>
    <section class="container">
        <!-- logo -->
        <div class="logo">
            <a href="#"><img src="../assets/img/dc-logo.png" alt="DC Logo"></a>
        </div>
        <!-- navbar -->
        <ul>
            <li v-for="(ref, index) in references" :key="index" :class="ref.current ? 'active' : ''">
                <a :href="ref.url" class="caps" :class="ref.current ? 'active' : ''">{{ref.text}}</a>
            </li>
        </ul>
    </section>
</template>

<script>
    export default {
        name: 'HeaderComponent',
        data() {
            return {
                //list of navbar items
                references: [
                    {
                    text: "characters",
                    url: "#",
                    current: false,
                },
                {
                    text: "comics",
                    url: "#",
                    current: true,
                },
                {
                    text: "movies",
                    url: "#",
                    current: false,
                },
                {
                    text: "tv",
                    url: "#",
                    current: false,
                },
                {
                    text: "games",
                    url: "#",
                    current: false,
                },
                {
                    text: "collectibles",
                    url: "#",
                    current: false,
                },
                {
                    text: "videos",
                    url: "#",
                    current: false,
                },
                {
                    text: "fans",
                    url: "#",
                    current: false,
                },
                {
                    text: "news",
                    url: "#",
                    current: false,
                },
                {
                    text: "shop",
                    url: "#",
                    current: false,
                },
                ],
                
            }
        },
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/variables.scss' as *;
@use '../assets/styles/partials/mixin.scss' as *;


section{
    height: 100px;
    @include my-flex-row;
    justify-content: space-between;
    ul{
        @include my-flex-row;

    }
    .logo{
        img{
            max-width: 100%;
            width: 80%;
        }
    }
    li{
        list-style: none;
        font-weight: 600;
        margin: 0.8rem;
        line-height: 100px;
        border-bottom: 4px solid transparent;

        .caps{
            text-transform: uppercase;
            text-decoration: none;
            color: $dark;
        }
        &:hover, &.active{
            cursor: pointer;
            a{
            color: $lightblue;

            }
            border-bottom: 4px solid $lightblue;
        }
    }
}

    


</style>