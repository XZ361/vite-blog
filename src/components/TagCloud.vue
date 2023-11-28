<template>
    <div class="tag-cloud">
        <h3>标签</h3>
        <div v-for="tag in tags " :key="tag">
            <router-link :to="{name:'Tag',params:{tag}}"> #{{ tag }}</router-link>
        </div>
    </div>
</template>

<script setup>
import { ref } from "vue";

const tags = ref([]);
const tagArray = new Set();

props.posts.forEach(item => {
    item.tags.forEach(item=>{
       tagArray.add(item);
    })
});
tags.value = [...tagArray];

const props = defineProps({
    posts:Array
})
</script>

<style lang="scss" scoped>
.tag-cloud{
    padding: 10px;
}
.tag-cloud h3{
    border-bottom: 1px solid #eee;
    padding: 16px 8px;
    color: #444;
    text-align: left;
}
.tag-cloud div{
    display: inline-block;
    padding: 10px;
    text-align: left;
}
.tag-cloud a{
    color: #ccc;
    text-decoration: none;
}
.tag-cloud a.router-link-active{
    color: #ff8800;
}
</style>