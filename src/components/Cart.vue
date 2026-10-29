<script setup>
import { inject, computed } from 'vue'
import CartItem from './CartItem.vue'
const cart = inject('cart')
const total = computed(() => cart.reduce((sum, p) => sum + p.price, 0))
const emptyCart = () => {
  cart.splice(0, cart.length)
}
</script>

<template>
  <section class="carrito">
    <h1>Carrito - {{ cart.length }}</h1>
    <div class="cart-items">
      <CartItem v-for="item in cart" :item="item" :key="item.name" />
    </div>
    <p>TOTAL: {{ total }}€</p>
    <button @click="emptyCart">Buida carret</button>
  </section>
</template>

<style scoped>
.carrito {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}
</style>
