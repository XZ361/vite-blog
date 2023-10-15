<template>
    <div>
        <h2>{{ name }}</h2>
    </div>
</template>

<script setup>
import { ref,reactive,computed } from "vue";
const name = computed(()=>{
    return '王二狗'
})
</script>

<style lang="scss" scoped>

</style>