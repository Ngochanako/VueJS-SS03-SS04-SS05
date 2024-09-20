<template>
  <div>
    <h3>Bài 10</h3>
    <button @click="handleClick">
        <div v-if="isCheck">Hiển thị</div>
        <div v-else>Ẩn</div>
    </button>
    <div>
    <div v-if="isCheck">Nội dung hiển thị</div>
    <div v-else>Nội dung Ẩn</div>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
    const isCheck = ref(true);
    const handleClick=()=>{
        isCheck.value =!isCheck.value;
    }
</script>

<style>

</style>