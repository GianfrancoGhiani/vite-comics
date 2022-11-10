<template>
    <header>
        <HeaderComponent />
    </header>
    <main>
        <BodyComponent />
    </main>
    <footer>
        <FooterComponent />
    </footer>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue';
import BodyComponent from './components/BodyComponent.vue';
import FooterComponent from './components/FooterComponent.vue';

    export default {
        components:{
            HeaderComponent,
            BodyComponent,
            FooterComponent,
        },
        data() {
            return {
                
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>