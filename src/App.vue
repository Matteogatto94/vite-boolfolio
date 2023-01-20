<script>
import ProjectCards from './components/ProjectCards.vue'

export default {
    components: {
        ProjectCards
    }
}
</script>

<template>
    <section class="vue-home">
        <div class="container">

            <h1>Projects:</h1>
            <div class="row row-cols-1 row-cols-sm-3 g-4">
                <router-view></router-view>
            </div>
        </div>
    </section>
</template>

<style lang="scss">
@use './styles/general.scss';
</style>
