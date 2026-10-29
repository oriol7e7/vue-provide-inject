<script setup>
import { reactive, provide } from 'vue'
import Cart from './components/Cart.vue'
import CategoryList from './components/CategoryList.vue'

const products = [
  { name: 'Auriculars Wireless 🎧', price: 50 },
  { name: 'Smartwatch ⌚', price: 120 },
  { name: 'Teclat Mecànic ⌨️', price: 80 },
  { name: 'Altaveu Bluetooth 🔊', price: 60 },
]
const cart = reactive([])

//Provide cart and products array to get them from anywhere
provide('cart', cart)
provide('products', products)
</script>

<template>
  <h1>Botiga de gadgets</h1>
  <main>
    <CategoryList />
    <Cart />
  </main>
</template>

<style scoped>
main {
  height: 80dvh;
  width: 100%;
  border-radius: 6px;
  border: solid 2px rgb(211, 179, 37);
  display: flex;
  justify-content: space-around;
}
</style>
