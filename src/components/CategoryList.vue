<script setup>
import { inject } from 'vue'
import ProductItem from './ProductItem.vue'

//Get the products of the provide in the app
const products = inject('products')
</script>

<template>
  <div class="category-list">
    <h2>Products</h2>
    <div class="products">
      <ProductItem v-for="p in products" :key="p.name" :product="p" />
    </div>
  </div>
</template>

<style scoped>
.products {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}
</style>
