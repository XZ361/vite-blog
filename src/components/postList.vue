<template>
    <div class="post-list">
        <div v-for="post in posts" :key="post.id">
            <h2>{{ post.title }}</h2>
        </div>
    </div>
</template>

<script setup>
defineProps({
    posts:Array
})
</script>

<style lang="scss" scoped>

</style>