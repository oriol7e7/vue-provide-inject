<script setup>
import { inject, defineProps } from 'vue'
const props = defineProps({
  product: {
    type: Object,
    required: true,
  },
})
const cart = inject('cart')
const addToCart = () => {
  cart.push(props.product)
  alert('Producte: ' + props.product.name + 'afegit al carret')
}
</script>

<template>
  <div class="product-item">
    <div class="product-info">
      <span class="name">{{ product.name }}</span>
      <span class="price">{{ product.price }}€</span>
    </div>
    <button @click="addToCart">Add to cart</button>
  </div>
</template>

<style scoped>
.product-item {
  display: flex;
  justify-content: space-around;
  align-items: center;
  border: solid 1px gray;
  border-radius: 6px;
  padding: 6px;
  gap: 1rem;
  transition: all 0.2s ease-in;
}
.product-item:hover {
  border: solid 1px rgb(111, 158, 40);
  transform: translateY(-2px);
}
.product-info {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 1rem;
}
button {
  padding: 14px;
  border-radius: 6px;
  border: none;
  background-color: greenyellow;
  color: black;
  font-weight: bold;
  cursor: pointer;
  font-size: 1rem;
}
</style>
