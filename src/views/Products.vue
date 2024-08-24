<template>
  <div class="products-container">
    <Sidebar />
    <div class="main-content">
      <Header />
      <div class="products-grid">
        <div
          class="product-card"
          v-for="(product, index) in products"
          :key="index"
          @click="goToProductDetail(index)"
        >
          <img :src="product.image" alt="Product Image" class="product-image" />
          <h3 class="product-name">{{ product.name }}</h3>
          <p class="product-price">{{ product.price }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { useRouter } from 'vue-router';
import Sidebar from '@/components/Sidebar.vue';
import Header from '@/components/Header.vue';

export default defineComponent({
  name: 'Products',
  components: {
    Sidebar,
    Header,
  },
  setup() {
    const router = useRouter();

    const products = [
  {
    id: 1,
    name: 'Product 1',
    price: '$25.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 2,
    name: 'Product 2',
    price: '$35.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 3,
    name: 'Product 3',
    price: '$45.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 4,
    name: 'Product 4',
    price: '$55.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 5,
    name: 'Product 5',
    price: '$65.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 6,
    name: 'Product 6',
    price: '$75.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 7,
    name: 'Product 7',
    price: '$85.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 8,
    name: 'Product 8',
    price: '$95.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 9,
    name: 'Product 9',
    price: '$105.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 10,
    name: 'Product 10',
    price: '$115.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 11,
    name: 'Product 11',
    price: '$125.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 12,
    name: 'Product 12',
    price: '$135.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 13,
    name: 'Product 13',
    price: '$145.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 14,
    name: 'Product 14',
    price: '$155.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 15,
    name: 'Product 15',
    price: '$165.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 16,
    name: 'Product 16',
    price: '$175.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 17,
    name: 'Product 17',
    price: '$185.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 18,
    name: 'Product 18',
    price: '$195.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 19,
    name: 'Product 19',
    price: '$205.99',
    image: 'https://via.placeholder.com/150',
  },
  {
    id: 20,
    name: 'Product 20',
    price: '$215.99',
    image: 'https://via.placeholder.com/150',
  },
];

    const goToProductDetail = (index: number) => {
      const productId = products[index].id;
      router.push(`/products/${productId}`);
    };

    return {
      products,
      goToProductDetail,
    };
  },
});
</script>

<style scoped>
.products-container {
  display: flex;
}

.main-content {
  flex: 1;
  padding: 20px;
  background-color: #f5f5f5;
}

.products-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
}

.product-card {
  background-color: #ffffff;
  border-radius: 12px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  padding: 20px;
  text-align: center;
  transition: transform 0.3s ease;
}

.product-card:hover {
  transform: translateY(-5px);
}

.product-image {
  width: 100%;
  border-radius: 8px;
  margin-bottom: 15px;
}

.product-name {
  font-size: 18px;
  color: #34495e;
  margin-bottom: 10px;
}

.product-price {
  font-size: 16px;
  font-weight: bold;
  color: #2ecc71;
}
</style>