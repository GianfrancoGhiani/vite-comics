<template>
    <div class="bg">
        <section class="container">
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
        </section>
        
    </div>
</template>

<script>
    export default {
        name: 'FooterComponent',
        data() {
            return {
                lists:[               
                    ['dc comics', 'characters', 'comics', 'movies', 'TV', 'games', 'videos', 'news'],
                    ['shop', 'shop DC', 'shop DC collectibles'],
                    ['dc', 'terms of use', 'privacy policy (new)', 'ad choices', 'advertising', 'jobs', 'subscriptions', 'talent workshop', 'CPSC certificates', 'ratings', 'shop help', 'contact us'],
                    ['sites', 'DC', 'MAD magazine', 'dc kids', 'dc universe', 'dc power visa'],
                    
                ]
            }
        },
    }
</script>

<style lang="scss" scoped>
@use '../assets/styles/partials/mixim.scss' as *;
@use '../assets/styles/partials/variables.scss' as *;

.bg{
    height: fit-content;
    background-image: url('../assets/img/footer-bg.jpg');
    overflow: hidden;


}
.container{
    height: 400px;
    padding: 3.5rem 0;
    @include my-flex-row;
    justify-content: space-between;
}

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
}

</style>