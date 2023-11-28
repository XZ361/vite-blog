<template>
    <div class="tag">
        <div v-if="posts.length">
            <Postlist :posts="postsWithTag" ></Postlist>
            <TagCloud :posts="posts"></TagCloud>
        </div>
    </div>
</template>

<script setup>
import { useRoute } from "vue-router";
import getPosts from "../composibles/getPosts";
import { computed } from "vue";
import Postlist from '../components/postList.vue'
import TagCloud from '../components/TagCloud.vue'

const route = useRoute();
const {posts,load} = getPosts();
load();

const postsWithTag = computed(()=>{
    return posts.value.filter(p=>p.tags.includes(route.params.tag));
})

</script>

<style lang="scss" scoped>

</style>