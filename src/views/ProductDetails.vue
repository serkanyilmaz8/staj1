<template>
    <div class="product-details">
      <img :src="product.image" alt="Product Image" />
      <h1>{{ product.name }}</h1>
      <p>{{ product.price }}</p>
      <p>{{ product.description }}</p>
    </div>
  </template>
  
  <script lang="ts">
  import { defineComponent } from 'vue';
  import { useRoute } from 'vue-router';
  
  export default defineComponent({
    name: 'ProductDetails',
    data() {
      return {
        product: {
          id: 0,
          name: '',
          price: '',
          image: '',
          description: ''
        }
      };
    },
    setup() {
      const route = useRoute();
      const productId = route.params.id;
  
      const products = [
        {
          id: 1,
          name: 'Product 1',
          price: '$25.99',
          image: 'https://via.placeholder.com/150',
          description: 'Description of Product 1'
        },
        // Diğer ürünler buraya eklenir
      ];
  
      const product = products.find(product => product.id === parseInt(productId as string));
  
      return {
        product: product || { id: 0, name: 'Not Found', price: '-', image: '', description: 'Product not found' }
      };
    },
  });
  </script>
  
  <style scoped>
  .product-details {
    max-width: 600px;
    margin: 0 auto;
    padding: 20px;
    background: white;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    border-radius: 8px;
    text-align: center;
  }
  
  .product-details img {
    max-width: 100%;
    border-radius: 8px;
    margin-bottom: 20px;
  }
  
  .product-details h1 {
    font-size: 24px;
    margin-bottom: 10px;
    color: #34495e;
  }
  
  .product-details p {
    font-size: 18px;
    margin-bottom: 10px;
    color: #2ecc71;
  }
  </style>