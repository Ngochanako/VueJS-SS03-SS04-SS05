<template>
    <div>
      <h3>SS5-Bài 10</h3>
      {{ list }}
      <br/>
      <button @click="handleClick">Random number</button>
    </div>

</template>

<script setup>
import { ref } from "vue";

   const list=ref([]);
   const handleClick=()=>{
      const number=Math.floor(Math.random()*100);
      list.value.push(number);
   }
</script>

<style>

</style>