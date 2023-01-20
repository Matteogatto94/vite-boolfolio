<script>
export default {
    name: 'NotFound'
}
</script>

<template>
    <div class="container">
        <p class="leed">
            Ops, Page not found!
        </p>
        <router-link :to="/">Go to HomePage</router-link>
    </div>
</template>

<style lang="scss" scoped>

</style>