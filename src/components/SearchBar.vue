<template>
    <div>
        <input type="text" v-model="val" >

        <p v-for="item,index in searchNums" :key="index">{{ item.name }}</p>

    </div>
</template>

<script setup>
import { ref,reactive,computed, watch, watchEffect } from "vue";
let nums = ref([{ name: 'hhl' }, { name: '44sg' }, { name: '33i' }, { name: '44t' }]);
let val = ref('')
const searchNums = computed(()=>{
    // includes()：返回布尔值，表示是否找到了参数字符串。
    return nums.value.filter((item)=>item.name.includes(val.value))
})

// 监听属性
// watch(val,(newVal,preVal)=>{
//     console.log('val改变了！',newVal,preVal);
// });
// 初始化就会执行
// watchEffect(()=>{
//     console.log('watchEffect执行了',val.value);
// })
</script>

<style lang="scss" scoped>

</style>