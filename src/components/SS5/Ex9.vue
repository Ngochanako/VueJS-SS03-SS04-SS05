<template>
   <div>
    <h3>SS5-Bài 9</h3>
    <h4>Gender: {{ gender }}</h4>
    <button @click="handleClick">Random Gender</button>
   </div>
</template>

<script setup>
import { ref } from "vue";

   const genderList = ['Nam', 'Nữ','Khác'];
   let gender=ref('Nam')
   
   const handleClick = () => {
      gender.value = genderList[Math.floor(Math.random() * genderList.length)];
   }
</script>

<style>

</style>