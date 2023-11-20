<script setup>
// import { ref } from 'vue'

// defineProps({
//   msg: String,
// })

// const count = ref(0)
</script>

<template>
  <!-- <h1>{{ msg }}</h1>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
    <p>
      Edit
      <code>components/HelloWorld.vue</code> to test HMR
    </p>
  </div> -->
  <header>
    <h1>个人博客</h1>
    <nav>
      <router-link to="/">首页</router-link>
      <router-link to="create">新建</router-link>
    </nav>
  </header>
</template>

<style scoped>
header{
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 10px;
}
header h1{
  color: #dfdfdf;
  font-size: 48px;
}
header a{
  color: #bbb;
  text-decoration: none;
  margin-left:20px ;
}
header a.router-link-active{
  color: #444;
  font-weight: bold;
}
</style>
