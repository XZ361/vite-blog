<script setup>
// setup是vue3语法糖，vue3兼容vue2
// import HelloWorld from './components/HelloWorld.vue'
import About from './views/About.vue'
import NavBar from './components/NavBar.vue'
import SearchBar from './components/SearchBar.vue'

</script>

<template>
  <NavBar/>
  <router-view></router-view>
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
