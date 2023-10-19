<script setup>
// setup是vue3语法糖，vue3兼容vue2
// import HelloWorld from './components/HelloWorld.vue'
import Home from './views/Home.vue'
import About from './views/About.vue'
import Compute from './components/Compute.vue'
import SearchBar from './components/SearchBar.vue'
import Postlist from './components/postList.vue'

let posts = [
  {title:'hello Vue',id:'001'},
  {title:'hello React',id:'002'}
]
</script>

<template>
  <Postlist :posts="posts"></Postlist>
  ------------------------
  <SearchBar></SearchBar>
  <Compute></Compute>
  <About></About>
  <p>hello vite</p>
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
