<template>
   <div>
    <h3>Bài 9</h3>
    <h3>Danh sách bài viết</h3>
    <div>
        <div v-for="(btn,index) in list" :key="index">
            <p>Id:{{ btn.id }}</p>
            <p>Title:{{ btn.title }}</p>
            <p>Content:{{ btn.content }}</p>
            <p>Author:{{ btn.author }}</p>
        </div>
    </div>
   </div>
</template>

<script setup>
const list=[
    {
        id:1,
        title:"Tại sao nên học JS",
        content:"Học để đi làm",
        author:"David"
    },
    {
        id:2,
        title:"Tại sao nên học Vue",
        content:"Học để đi làm",
        author:"Lica"
    }
]
</script>

<style>

</style>