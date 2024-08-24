<template>
    <header class="header">
      <input type="text" placeholder="Search..." />
      <div class="user-info">
        <img src="https://via.placeholder.com/40" alt="User Avatar" />
        <span>Aurora Shenton</span>
      </div>
    </header>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    name: 'Header',
  });
  </script>
  
  <style scoped>
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
    background-color: #ffffff;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
  }
  
  .header input[type="text"] {
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    width: 300px;
  }
  
  .user-info {
    display: flex;
    align-items: center;
  }
  
  .user-info img {
    border-radius: 50%;
    margin-right: 10px;
  }
  </style>