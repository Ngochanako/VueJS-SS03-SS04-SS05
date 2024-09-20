<template>
    <div> 
        <h3>Bài 2</h3>
        <p>Company:{{ company.name }}</p>
        <p>Age:{{ company.age }}</p>
        <button @click="handleClick">Change data</button>
    </div>
</template>

<script setup>
import { reactive } from "vue";
  
  let company=reactive({
    name:'Rikkei Academy',
    age:20
  })
 const handleClick=()=>{
    company.name='Rikkei Academy Inc.'
    company.age=25
 }
</script>

<style>

</style>