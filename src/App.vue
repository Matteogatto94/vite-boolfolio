<script>
import ProjectCards from './components/ProjectCards.vue'
import axios from 'axios'

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
                <ProjectCards />
            </div>
        </div>
    </section>
</template>

<style lang="scss">
@use './styles/general.scss';
</style>
