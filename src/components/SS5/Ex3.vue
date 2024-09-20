<template>
    <div>
        <h3>SS5-Bài3</h3>
        <select @change="handleChange" name="" id="">
            <option value="0">Chọn quyền</option>
            <option value="1">Admin</option>
            <option value="2">User</option>
        </select>

        <div>
            Quyền hạn của bạn là :{{ userRole }}
        </div>
    </div>
</template>

<script setup>
   import {ref} from 'vue'
      const userRole=ref('');
   const handleChange=(e)=>{
      if(e.target.value=='0'){
         userRole.value='';
      }else if(e.target.value=='1'){
         userRole.value='Admin';
      }else{
         userRole.value='User';
      }
   }
</script>

<style>

</style>