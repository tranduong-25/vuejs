<template>
  
    <h1>Thoi gian hien tai: {{ time }}</h1>
  
</template>

<script setup>
import {  onBeforeUnmount, onMounted, ref } from 'vue';
let timerId;

const formatDate = (date)=> {
    
    const today = new Date (date);

    const hours = today.getHours().toString().padStart(2, 0);
    const minutes = today.getMinutes().toString().padStart(2, 0);
    const seconds = today.getSeconds().toString().padStart(2, 0);
    return `${hours}:${minutes}:${seconds}`;
};

const time = ref(formatDate(new Date()));

onMounted(() => {
    setInterval(() => {
        time.value = formatDate(new Date());
    },1000)
})

onBeforeUnmount(() => {
    clearInterval(timerid)
})

</script>

<style>

</style>