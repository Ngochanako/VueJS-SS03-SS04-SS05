<template>
  <h3>Bài 4</h3>
  <input type="text" v-model="valueInput">
   
</template>

<script setup>
import { watch,ref } from "vue";

const valueInput=ref('');
watch(valueInput,()=>{
    console.log(valueInput.value);
    
})
</script>

<style>

</style>