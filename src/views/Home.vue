<template>
    <div>
        <h1>Home</h1>
        <p>{{ name }} -- {{ age }}</p>
        <button @click="handleClcik">click</button><br>
        <button @click="handleClcik2">click2</button><br>
        <p>{{ str }} -- {{ num }}</p>

        <button @click="handleClcik3">click3</button>
    </div>
</template>

<script setup>
import { ref } from "vue";
// 定义属性和方法
// 这种方式虽然可以，但是存在问题；
let name = '吴老二';
let age = 28;
const handleClcik = () => {
  console.log(name);
}
// 当我们改变定义的属性，会发现属性改变了，但是页面无法监听到并进行及时的同步更新
const handleClcik2 = () => {
  name = 'mr.bl';
  age = 10;
  console.log(name,age);
}
// 要解决上述问题，我们需要引入v3中的ref模块,以便实现响应式数据
let str = ref('hello');
let num = ref(20);
const handleClcik3 = () => {
  // 可以发现str是个对象
  // console.log(str);
  str.value = 'hello vite!';
  num.value = 30;
}
</script>

<style lang="scss" scoped>

</style>