<template>
    <div>
        <h1>Home</h1>
        <p>{{ name }} -- {{ age }}</p>
        <button @click="handleClcik">click</button>
        <button @click="handleClcik2">click2</button>
    </div>
</template>

<script setup>
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
</script>

<style lang="scss" scoped>

</style>