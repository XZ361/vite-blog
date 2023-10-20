<template>
    <div>
        <h3> {{ post.title }}</h3>
        <p>{{ snippet }}</p>
    </div>
</template>

<script setup>
import { computed } from 'vue';
const getPost = defineProps({
    post:Object
})
const snippet = computed(()=>{
    // console.log(getPost.post);
    return getPost.post.body.substring(0,100)+'...';
})
</script>

<style lang="scss" scoped>

</style>