<template>
   <div>
    <h3>Bài 2-SS5</h3>
    <button @click="handleClick">
        <div v-if="isShow">Hiện</div>
        <div v-else>Ẩn</div>
    </button>
   </div>
</template>

<script setup>
import { ref } from "vue";

    const isShow=ref(true);
    const handleClick=()=>{
        isShow.value=!isShow.value;
    }
</script>

<style>

</style>