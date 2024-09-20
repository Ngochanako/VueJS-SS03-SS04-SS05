<template>
   <div class="container">
    <h3>SS6-Bài tập tổng hợp</h3>
    <form @submit.prevent="onSubmit" class="form">
        <div class="nav">
           <input type="text" placeholder="Enter your job" v-model="valueInput">
           <button type="submit" @click="addTask" style="border: 1px solid transparent;background-color: rgb(198, 190, 190); color: white; cursor: pointer;">Add Job</button>
        </div>
        <div v-if="notify" style="color: red;">Công việc không được để trống</div>
        <!-- render all task start -->
        <div v-if="filterList.length>0" class="list">
            <div class="list-item" v-for="(btn,index) in filterList" :key="index">
                <div style="display: flex; gap: 10px;">
                    <input @click="handleTask(btn.id)" :checked=" btn.status" type="checkbox" name="" id="">
                    {{ btn.detail }}
                </div>                
                <button @click="handleDelete(btn.id)" style="background-color: red;color: white; border: transparent">Delete</button>
            </div>   
        </div>
        <!-- render all task end -->
         <button style="border:1px solid salmon;background-color: rgb(198, 190, 190);color: white;">Số công việc hoàn thành:{{ taskDone }}/{{ list.length }} công việc</button>
    </form>
   </div>
</template>

<script setup>
import { computed, ref, watch } from "vue";
   const list=ref(JSON.parse(localStorage.getItem('listTask'))||[]);
   const valueInput=ref("");
   const taskDone=computed(()=>list.value.filter(btn=>btn.status).length);
   const filterList=computed(()=>list.value);
   const notify=ref(false);
    watch(valueInput,()=>{notify.value=false});
   const addTask=()=>{
      if(valueInput.value){
          let newTask={
            id:Math.floor(Math.random()*100000000),
            detail:valueInput.value,
            status:false,
          }
          list.value.push(newTask);
            localStorage.setItem('listTask',JSON.stringify(list.value));
            valueInput.value="";
      }else{
        notify.value=true;
      }
   }
   const handleDelete=(id)=>{
     list.value=list.value.filter(btn=>btn.id!==id);
     localStorage.setItem('listTask',JSON.stringify(list.value));
   }
   const handleTask=(id)=>{
    list.value=list.value.map(btn=>btn.id===id?{...btn,status:!btn.status}:btn);
    localStorage.setItem('listTask',JSON.stringify(list.value));
   }
</script>

<style scoped>
.conatiner{
    display: flex;
    justify-content: center;
    align-items: center;
}
.form{
    display: flex;
    flex-direction: column;
    gap: 10px;
    width: 400px;
    padding: 10px;
    border: 1px solid rgb(207, 203, 203);
    box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.5);
    border-radius: 5px;
}
.nav{
    display: flex;
    justify-content: space-between;
    align-items: center;
    
}
input{
    border: 1px solid rgb(198, 190, 190);
    border-radius: 5px;
    padding: 5px;
    color: rgb(198, 190, 190);
    cursor: pointer;
}
input:focus{
    outline: none;
}
button{
    padding: 5px;
    border-radius: 5px;
}
.list{
    display: flex;
    flex-direction: column;
    gap: 10px;
}
.list-item{
    display: flex;
    justify-content: space-between;
    align-items: center;
}
</style>