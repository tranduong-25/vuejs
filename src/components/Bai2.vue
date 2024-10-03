<template>
    <div>
      <h1>Bai2:</h1>
      <input type="text" v-model="inputValue">
      <h2>Count: {{ count }}</h2>
      <button @click="handleCount">Counter</button>
    </div>
  </template>
  
  <script setup>
  import { ref, onBeforeMount } from 'vue';
  
  const count = ref(0);
  const inputValue = ref("");
  const handleCount = () => {
    count.value++;
  };
  
  onBeforeMount(() => {
    count.value = 0;
    console.log("du lieu da thay doi");
  });
  </script>
  
  <style>

  </style>
  