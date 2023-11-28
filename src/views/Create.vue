<template>
    <div class="create">
        <form @submit.prevent="handleSubmit">
            <label for="title">标题</label>
            <input type="text" v-model="title" required>
            <label for="body">内容</label>
            <textarea v-model="body" required></textarea>
            <label for="tag">标签(回车添加tag)</label>
            <input type="text" v-model="tag" @keydown.enter.prevent="addTag">
            <!-- 显示tag-->
            <div v-for="tag in tags" :key="tag" class="pill">#{{ tag }}</div>
        </form>
        <button @click="handleSubmit"> 添加</button>
    </div>
</template>

<script setup>
import { ref } from "vue";
import axios from "axios";
import { useRouter } from "vue-router";

const title = ref("");
const body = ref("");
const tags = ref([]);
const tag = ref("");
const router = useRouter();

const addTag = ()=>{
    if(!tags.value.includes(tag.value)){
        tag.value = tag.value.replace(/\s/g,"");
        tags.value.push(tag.value);
    }
    tag.value = "";
}
const handleSubmit = async ()=>{
    const post={
        id: Math.floor(Math.random()*1000),
        title: title.value,
        body: body.value,
        tags: tags.value
    }
    let data = await axios.post("http://localhost:3000/posts",post);
    // 在 HTTP 协议中，201 Created 是一个代表成功的应答状态码，表示请求已经被成功处理，并且创建了新的资源。新的资源在应答返回之前已经被创建。同时新增的资源会在应答消息体中返回，
    if(data.status == 201){
        router.push('/');
    }
}
</script>

<style lang="scss" scoped>
form{
    max-width: 480px;
    margin: 0px auto;
    text-align: left;
}
input,textarea{
    display: block;
    margin: 10px 0;
    width: 100%;
    box-sizing: border-box;
    padding: 10px;
    border: 1px solid #eee;
}
textarea{
    height: 160px;
}
label{
    display: inline-block;
    margin-top: 30px;
    position: relative;
    font-size: 20px;
    margin-bottom: 10px;
}
button{
   display: block; 
   margin-top: 30px;
   background: #ff8800;
   color: white;
   border:none;
   padding: 8px 16px;
   font-size: 18px;
}
.pill{
    display: inline-block;
    margin: 10px 10px 0 0;
    color: #444;
    background: #ddd;
    padding: 8px;
    border-radius: 20px;
    font-size:14px
}
</style>