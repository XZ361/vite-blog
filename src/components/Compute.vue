<template>
    <div>
        <h2>{{ name }}</h2>
        <ul>
            <li v-for="(item, index) in nums" :key="index">{{ item.name }}</li>
        </ul>
        <!-----------双向数据绑定-->
        <input type="text" v-model="vut">
        <p>{{ vut }}</p>
    </div>
</template>

<script setup>
import { ref, reactive, computed } from "vue";
const name = computed(() => {
    return '王二狗'
})
let nums = ref([{ name: '33' }, { name: '44' }, { name: '33i' }, { name: '44t' }]);
let vut = ref('hello model')
</script>

<style lang="scss" scoped></style>