<script setup>
// setup是vue3语法糖，vue3兼容vue2
// import HelloWorld from './components/HelloWorld.vue'
import Home from './views/Home.vue'
import About from './views/About.vue'
import Compute from './components/Compute.vue'
import SearchBar from './components/SearchBar.vue'
import Postlist from './components/postList.vue'
import { ref } from 'vue'

let posts = ref([
  {title:'hello Vue',body:'hi Vue',id:1},
  {title:'hello React',body:'hi React Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolor, temporibus cumque numquam tenetur praesentium aliquam debitis rerum maxime quia sunt, magni laborum molestias eveniet voluptates ipsam iste iusto a. Quam?',id:2}
]);
const showBar = ref(true);
</script>

<template>
  <Postlist :posts="posts"  v-if= "showBar"></Postlist>
  <button @click="showBar = !showBar">显示或隐藏</button>
  <button @click="posts.pop()">删除一条数据</button>
  ------------------------
  <SearchBar></SearchBar>
  <Compute></Compute>
  <About></About>
  <!-- <Home></Home> -->
  
  <!-- <div>
    <a href="https://vitejs.dev" target="_blank">
      <img src="/vite.svg" class="logo" alt="Vite logo" />
    </a>
    <a href="https://vuejs.org/" target="_blank">
      <img src="./assets/vue.svg" class="logo vue" alt="Vue logo" />
    </a>
  </div>
  <HelloWorld msg="Vite + Vue" /> -->
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
