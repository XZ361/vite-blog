<template>
    <div class="post-list">
        <div v-for="post in posts" :key="post.id">
            <SinglePost :post="post"></SinglePost>
        </div>
    </div>
</template>

<script setup>
import SinglePost  from "./SinglePost.vue";
import { onMounted,onUnmounted,onUpdated } from "vue";

defineProps({
    posts:Array
})

onMounted(()=>{
    // 可以在次生命周期进行数据请求 
    // alert('页面挂载/渲染之前执行');
})

onUnmounted(()=>{
    // alert('组件销毁之前执行');
})
onUpdated(()=>{
    alert('当组件内的内容发生变化，就会执行该钩子函数')
})
</script>

<style lang="scss" scoped>

</style>