<template>
    <div>
      <h1>Current Company: {{ currentCompany }}</h1>
      <h2>Age: {{ age }}</h2>
      <button @click="updateRandomAge">Random</button>
    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue';
  
  // Initialize age with a default value of 1
  const age = ref(1);
  
  // Array containing company names
  const companies = ['Rikkei Academy', 'Rikkei Education', 'Rikkei Fukuoka'];
  
  // Computed property to determine the current company based on the age
  const currentCompany = computed(() => {
    return companies[(age.value - 1) % companies.length]; // Use modulus to rotate companies based on age
  });
  
  // Function to generate a random age between 1 and 10
  const updateRandomAge = () => {
    age.value = Math.floor(Math.random() * 10) + 1; // Random number between 1 and 10
  };
  </script>
  
  <style>
  button {
    background-color: blue;
    color: white;
    border: none;
    padding: 10px;
    cursor: pointer;
    border-radius: 5px;
  }
  </style>
  