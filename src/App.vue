<script>
import ProjectCards from './components/ProjectCards.vue'
import AppNav from './components/AppNav.vue'

export default {
    components: {
        ProjectCards,
        AppNav
    }
}
</script>

<template>
    <AppNav></AppNav>
    <router-view></router-view>
</template>

<style lang="scss">
@use './styles/general.scss';
</style>
