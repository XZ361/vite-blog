<template>
    <div>
        <h1>Home</h1>
        <p>{{ name }} -- {{ age }}</p>
        <button @click="handleClcik">click</button><br>
        <button @click="handleClcik2">click2</button><br>
        <p>{{ str }} -- {{ num }}</p>

        <button @click="handleClcik3">click3</button>
        <!-------------------------------------------------------->
        <!-- 注意，在模板中使用 ref 时，我们不需要附加 .value。为了方便起见，当在模板中使用时，ref 会自动解包 -->
        <p>{{ refData.name }} -- {{ refData.age }}</p>
        <button @click="handleClcik4">click4</button>
        <p>{{ reactiveData.name }} -- {{ reactiveData.age }}</p>
        <button @click="handleClcik5">click5</button>
    </div>
</template>

<script setup>
import { ref } from "vue";
import { reactive } from "vue";
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
// ref() 接收参数，并将其包裹在一个带有 .value 属性的 ref 对象中返回
let str = ref('hello');
let num = ref(20);
const handleClcik3 = () => {
  // 可以发现str是个对象
  // console.log(str);
  str.value = 'hello vite!';
  num.value = 30;
}
// v3给我们提供了reactive模块，另一种声明响应式状态的方式，
// 即使用 reactive() API。与将内部值包装在特殊对象中的 ref 不同，reactive() 将使对象本身具有响应性：
let refData = ref({name:'hello',age:11});
const handleClcik4 = () => {
  // console.log(str);
  refData.value.name = 'hello vite!';
  refData.value.age = 33;
}

let reactiveData = reactive({name:'vitehello',age:22});
const handleClcik5 = () => {
  console.log(reactiveData);
  reactiveData.name = 'HelloVite!';
  reactiveData.age = 33;
}
</script>

<style lang="scss" scoped>

</style>