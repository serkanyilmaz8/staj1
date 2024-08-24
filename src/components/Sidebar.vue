<template>
    <div class="sidebar">
      <div class="logo">
        <img src="@/assets/logo.svg" alt="Logo" />
        <h2>Pragmatic</h2>
      </div>
      <nav>
        <ul>
          <li><router-link to="/dashboard">Dashboard</router-link></li>
          <li><router-link to="/products">Products</router-link></li>
          <!-- Diğer menü öğeleri -->
        </ul>
      </nav>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    name: 'Sidebar',
  });
  </script>
  
  <style scoped>
  .sidebar {
    width: 250px;
    background-color: #333;
    color: white;
    padding: 20px;
  }
  
  .logo {
    text-align: center;
    margin-bottom: 20px;
  }
  
  .logo img {
    width: 50px;
  }
  
  nav ul {
    list-style: none;
    padding: 0;
  }
  
  nav ul li {
    margin: 15px 0;
  }
  
  nav ul li a {
    color: white;
    text-decoration: none;
  }
  
  nav ul li a:hover {
    text-decoration: underline;
  }
  </style>