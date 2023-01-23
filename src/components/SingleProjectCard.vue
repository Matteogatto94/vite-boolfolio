<script>
import { store } from '../store.js'
export default {
    name: 'SingleProjectCard',
    props: {
        project: Object
    },
    data() {
        return {
            store
        }
    },
    methods: {
        getImagePath(path) {
            console.log(path);
            if (path) {
                return this.store.base_api_url + '/storage/' + path
            } else {
                return 'https://via.placeholder.com/150'
            }
        }
    }
}
</script>

<template>
    <div class="col">
        <div class="card border-0 shadow-sm rounded-0 rounded-bottom">
            <img :src="getImagePath(project.cover_image)" class="card-image rounded-top" alt="">
            <div class="card-body">
                <h4>{{ project.title }}</h4>
                <p>{{ project.body }}</p>
                <router-link :to="{ name: 'single-project', params: { slug: project.slug } }">Read
                    More</router-link>
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
</template>

<style lang="scss" scoped>

</style>