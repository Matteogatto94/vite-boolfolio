<script>
import axios from 'axios'
export default {
    name: 'ProjectCards',
    data() {
        return {
            projects: [],
            base_api_url: 'http://localhost:8000',
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
        },
        getImagePath(path) {
            console.log(path);
            if (path) {
                return this.base_api_url + '/storage/' + path
            } else {
                return 'https://via.placeholder.com/150'
            }
        }
    },
    mounted() {
        this.getProjects(this.base_api_url + '/api/projects');
    }
}
</script>

<template>
    <section class="vue-home">
        <div class="container">

            <h1>Projects:</h1>

            <div class="row row-cols-1 row-cols-sm-3 g-4">
                <div class="col" v-for="project in projects.data">
                    <div class="card border-0 shadow-sm rounded-0 rounded-bottom">
                        <img :src="getImagePath(project.cover_image)" class="card-image rounded-top" alt="">
                        <div class="card-body">
                            <h4>{{ project.title }}</h4>
                            <p>{{ project.body }}</p>
                            <a href="#">Read More</a>
                        </div>

                        <div class="card-footer">
                            <div class="category">
                                <strong>Category: </strong>
                                <span v-if="project.category != null">
                                    {{ project.category.name }}
                                </span>
                                <span v-else>Uncategorized</span>
                            </div>
                            <div class="technologies">
                                <strong>Technologies: </strong>
                                <template v-if="project.technologies.length > 0">
                                    <span v-for="technology in project.technologies">
                                        #{{ technology.name }}
                                    </span>
                                </template>
                                <template v-else>
                                    <span>No technologies.</span>
                                </template>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style lang="scss">

</style>