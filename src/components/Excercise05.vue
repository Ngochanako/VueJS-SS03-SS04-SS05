<template>
    <div>
        <h3>Bài 5</h3>
        <h3>Giỏ hàng</h3>
        <ul>
            <li>Mèn mén loại 1- Số lượng :{{ cnt1 }} <button @click="handleClick1">Tăng số lượng</button></li>
            <li>Mèn mén loại 1- Số lượng :{{ cnt2 }} <button @click="handleClick2">Tăng số lượng</button></li>
            <li>Mèn mén loại 1- Số lượng :{{ cnt3 }} <button @click="handleClick3">Tăng số lượng</button></li>
        </ul>
        <div>Tổng số lượng sản phẩm :{{ sum }}</div>
    </div>
</template>

<script setup>
import { computed ,ref} from "vue";

    let cnt1=ref(1);
    let cnt2=ref(1);
    let cnt3=ref(1);
   const handleClick1=()=>{
     cnt1.value++
   }
   const handleClick2=()=>{
     cnt2.value++
   } 
   const handleClick3=()=>{
     cnt3.value++
   }
   const sum=computed(()=>{
      const s=(a,b,c)=>{
        return a+b+c;
      }
      return s(cnt1.value, cnt2.value, cnt3.value);
   })
</script>

<style>

</style>