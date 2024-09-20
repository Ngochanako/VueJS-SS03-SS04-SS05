<template>
  <div>
    <h3>Bài 1</h3>
    <button @click="handleClick">CLick {{ count }} lần</button>
  </div>
</template>

<script setup>
import {ref} from 'vue';
let count =ref(0);
const handleClick=()=>{
    count.value++;
}
</script>

<style>

</style>