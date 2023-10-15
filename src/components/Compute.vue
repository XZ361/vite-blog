<template>
    <div>
        <h2>{{ name }}</h2>
        <ul>
            <li v-for="(item, index) in nums" :key="index">{{ item.name }}</li>
        </ul>
    </div>
</template>

<script setup>
import { ref, reactive, computed } from "vue";
const name = computed(() => {
    return '王二狗'
})
let nums = [{ name: '33' }, { name: '44' }, { name: '33i' }, { name: '44t' }]
</script>

<style lang="scss" scoped></style>