<template>
   <div>
    <h3>SS5-Bài 7</h3>
    <button :class="{active:activeIndex===1}" @click="handleClick(1)">Button 1</button>
    <button :class="{active:activeIndex===2}" @click="handleClick(2)">Button 2</button>
    <button :class="{active:activeIndex===3}" @click="handleClick(3)">Button 3</button>
   </div>
</template>

<script setup>
import { ref } from "vue";

    const activeIndex = ref(1);
    const handleClick = (index) => {
        activeIndex.value = index;
    }
</script>

<style scoped>
.active{
    background-color: red;
    color: white;
    border: transparent;
}
</style>