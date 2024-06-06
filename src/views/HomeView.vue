<template>
    <div id="app">
        <NavigationBar />
        <AboutComponent />
        <FooterComponent />
    </div>
</template>

<script>
import AboutComponent from '@/components/base-components/AboutComponent.vue'
import NavigationBar from '@/components/base-components/NavigationBar.vue'
import FooterComponent from '@/components/base-components/FooterComponent.vue'

export default {
    name: 'HomeView',
    computed: {
        route() {
            return this.$route.path
        }
    },
    components: {
        NavigationBar,
        AboutComponent,
        FooterComponent
    }
}
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>