<template>
    <!-- footer divided into 2 pts -->
    <!-- the big one -->
    <section class="bg">
        <div class="container">
            <div class="lists">
                <ul v-for="(list, index) in lists" :key="index">
                    <li v-for="(elem, index) in list" :key="index" >
                        <a href="#" :class="{'list-title': (!index)}">{{elem}}</a>
                    </li>
                </ul>
            </div>
            <div class="big-logo">
                <img src="../assets/img/dc-logo-bg.png" alt="DC logo">
            </div>
        </div>
    </section>
    <!-- end page part -->
    <section class="bottom">
        <div class="container">
            <button class="btn">sign-up now!</button>
            <div class="social">
                <span>follow us</span>
                <div>
                    <img v-for="(social, index) in socials" :src="getPath(social)" :key="index" :alt="social.name">
                </div>

                

            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: 'FooterComponent',
        data() {
            return {
                // list of lists of references
                lists:[               
                    ['dc comics', 'characters', 'comics', 'movies', 'TV', 'games', 'videos', 'news'],
                    ['shop', 'shop DC', 'shop DC collectibles'],
                    ['dc', 'terms of use', 'privacy policy (new)', 'ad choices', 'advertising', 'jobs', 'subscriptions', 'talent workshop', 'CPSC certificates', 'ratings', 'shop help', 'contact us'],
                    ['sites', 'DC', 'MAD magazine', 'dc kids', 'dc universe', 'dc power visa'],
                    
                ],
                socials:[
                    {
                        name: 'facebook',
                        path: '../assets/img/footer-facebook.png'
                    },
                    {
                        name: 'twitter',
                        path: '../assets/img/footer-twitter.png'
                    },
                    {
                        name: 'youtube',
                        path: '../assets/img/footer-youtube.png'
                    },
                    {
                        name: 'pinterest',
                        path: '../assets/img/footer-pinterest.png'
                    },
                    {
                        name: 'periscope',
                        path: '../assets/img/footer-periscope.png'
                    },
                    
                ]
            }
        },
        methods: {
            getPath(social){
                return new URL(social.path, import.meta.url).href;
            }
        },
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/mixin.scss' as *;
@use '../assets/styles/partials/variables.scss' as *;
@use '../assets/styles/general.scss' as *;

// big part
.bg{
    height: fit-content;
    background-image: url('../assets/img/footer-bg.jpg');
    overflow: hidden;
    .container{
        height: 400px;
        padding: 3.5rem 0;
        @include my-flex-row;
        justify-content: space-between;
        .lists{
            width: 50%;
            height: 100%;
            margin-left: -1rem;
            @include my-flex-row;
            align-items: flex-start;
            flex-flow: column wrap;
            ul{
                list-style: none;
                margin: 1rem;
                li{
                    a{
                        text-decoration: none;
                        color: $grey-text;
                        text-transform: capitalize;
                        
                    }
                    :hover{
                            color: $white;
                        }
                    .list-title{
                        text-transform: uppercase;
                        color: $white;
                        font-weight: 800;
                    }
                }
            }
    }}
}
// end part
.bottom{
    background-color: $grey-footer-bg;
    height: 100px;
    @include my-flex-row;

    .container{
        @include my-flex-row;
        justify-content: space-between;
        .btn{
            padding: 1rem;
            font-weight: 700;
            text-transform: uppercase;
            background-color: transparent;
            color: $white;
            border-color: $lightblue;

            
            &:hover{
                background-color: lighten($color: $grey-footer-bg, $amount: 10);
                cursor: pointer;
            }
        }
        .social{
            @include my-flex-row;

            span{
                text-transform: uppercase;
                font-weight: 700;
                color: $lightblue;
                margin: 1.5rem;
                &:hover{
                    color: darken($color: $lightblue, $amount: 10);
                    cursor: pointer;
                }
            }
            div{
                @include my-flex-row;
                img{
                    margin: 0.3rem;
                    &:hover{
                        filter: brightness(1.3);
                        cursor: pointer;
                    }
                }
            }
    }}
}



</style>