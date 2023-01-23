<script>
import axios from 'axios'
import { store } from '../store.js'

export default {
    name: 'SingleProjectView',
    data() {
        return {
            project: [],
            store
        }
    },
    mounted() {
        //console.log(this.$route.params.slug);
        const url = this.store.api_base_url + '/api/projects/' + this.$route.params.slug
        console.log(url);
        axios.get(url)
            .then(response => {
                if (response.data.success) {
                    this.project = response.data.project
                } else {
                    this.$router.push({ name: 'not-found' })
                }
                console.log(response);
            }).catch(error => {
                console.error(error);
            })
    }
}
</script>

<template>
    <div class="container">
        <h1>{{ $route.params.slug }}</h1>
        <h2>{{ project.title }}</h2>
        <p>{{ project.body }}</p>
    </div>
</template>

<style lang="scss" scoped>

</style>