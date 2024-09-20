<template>
  <div>
    <h3>Bài 6</h3>
    <input type="number" v-model="valueInput">
    <button @click="handleClick">Add to Cart</button>
    <div>Tiền vừa thêm vào giỏ hàng:{{ moneyAdd  }}</div>
    <div>Tổng tiền giỏ hàng:{{ moneySum }}</div>
  </div>
</template>

<script setup>
import { computed, ref, watch } from "vue";

const valueInput=ref('') ;
const moneyAdd=ref(0) ;
const moneyTotal=ref(0);
const handleClick=()=>{
    moneyAdd.value=+valueInput.value;
    moneyTotal.value+=moneyAdd.value;
    valueInput.value=0;
}
const moneySum=computed(()=>{
    return moneyTotal.value
})
</script>

<style>

</style>