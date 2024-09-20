<template>
   <div>
    <h3>Bài 3</h3>
    <p>Acreage: {{ product}}</p>
    <button @click="handleClick">Change data</button>
   </div>
</template>

<script setup>
import { computed,ref } from "vue";

let width=ref(10);
let height=20;
const handleClick=()=>{
    width.value+=10;
}
const product=computed(()=>{
    const tich=(w)=>{
        return w*height;
    }
    return tich(width.value);
})
</script>

<style>

</style>