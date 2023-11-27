<template>
    <div class="post" v-if="post">
        <h3>{{ post.title }}</h3>
        <p class="pre">{{ post.body }}</p>
    </div>
    <div v-else>
        <Spinner/>
    </div>
</template>

<script setup>
import getPost from '../composibles/getPost'
import Spinner from "../components/Spinner.vue";

const {post,load} = getPost(props.id);

load();

const props = defineProps({
    id: Number
})
</script>

<style lang="scss" scoped>
.tags a{
    margin-right: 10px;
}
.post{
    max-width: 1200px;
    margin: 0 auto;
}
.post p{
    color: #444;
    line-height: 1.5em;
    margin-top: 40px;
}
.pre{
    white-space: pre-wrap;
}
.post h3{
    display: inline-block;
    position: relative;
    font-size: 26px;
    color: white;
    margin-bottom: 10px;
    max-width: 400px;
}
.post h3::before{
    content: "";
    display: block;
    width: 100%;
    height: 100%;
    position: absolute;
    background: #ff8800;
    z-index: -1;
    padding-right: 40px;
    left: -30px;
}
</style>