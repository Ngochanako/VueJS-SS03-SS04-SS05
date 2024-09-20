<template>
    <div>
        <h3>Bài 7</h3>
        <input type="number" v-model="valueInput">
        <button @click="handleClick">Tính bình phương</button>
        <div>Giá trị number:{{ valueNumber }}</div>
        <div>Giá trị bình phương:{{ valuePower }}</div>
    </div>
</template>

<script setup>
import { watch ,ref} from "vue"

   const valueInput=ref(0);
   const valueNumber=ref(0);
   const valuePower=ref(0);
   const handleClick=()=>{
      valueNumber.value=Number(valueInput.value);
      valuePower.value=Math.pow(valueNumber.value,2);
 
   }
   watch(valueInput,(newVal)=>{
    console.log('Giá trị number:',newVal); 
   })
</script>

<style>

</style>