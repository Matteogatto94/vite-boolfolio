<script>
import axios from 'axios'
import { store } from '../store.js'
import SingleProjectCard from './SingleProjectCard.vue'

export default {
    name: 'ProjectCards',
    components: {
        SingleProjectCard
    },
    data() {
        return {
            projects: [],
            store,
            loading: true,
            error: null
        }
    },
    methods: {
        getProjects(url) {
            axios
                .get(url)
                .then(response => {
                    console.log(response.data);
                    this.projects = response.data;
                    this.loading = false
                })
                .catch(error => {
                    console.error(error)
                    this.error = error.message
                    this.loading = false
                })
        }
    },
    mounted() {
        this.getProjects(this.store.base_api_url + '/api/projects');
    }
}
</script>

<template>
    <section class="vue-home">
        <div class="container">

            <h1>Projects:</h1>

            <div class="row row-cols-1 row-cols-sm-3 g-4">
                <SingleProjectCard :project="project" v-for="project in projects.data" />
            </div>
        </div>
    </section>
</template>

<style lang="scss">

</style>