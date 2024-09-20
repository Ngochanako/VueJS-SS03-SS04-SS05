<template>
     <div>
        <h3>SS5-Bài 5</h3>
        <div v-for="btn in arr" :key="btn">
            <div v-if="btn%2==0">{{ btn }}</div>
        </div>
     </div>
</template>

<script setup>
  const arr = [1, 2, 3, 4, 5, 8]
</script>

<style>

</style>