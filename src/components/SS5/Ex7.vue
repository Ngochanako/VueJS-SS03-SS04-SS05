<template>
    <div>
        <h3>SS5-Bài 8</h3>
        <button @click="sortInc">Tăng dần</button>
        <button @click="sortDesc">Giảm dần</button>
        <div style="display: flex;gap: 10px;">
        <div v-for="(btn,index) in list" :key="index">
            <button>{{btn}}</button>
        </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from "vue";

   const list=ref([3,1,2,6,5]);
   const sortDesc=()=>{
     list.value.sort((a,b)=>b-a);
   }
   const sortInc=()=>{
     list.value.sort((a,b)=>a-b);
   }
</script>

<style>

</style>