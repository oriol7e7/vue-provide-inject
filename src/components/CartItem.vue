<script setup>
const props = defineProps({
  item: {
    type: Object,
    required: true,
  },
})

</script>

<template>
  <div class="cart-item">
    <span>{{ props.item.name }} - {{ props.item.price }}€</span>
  </div>
</template>

<style scoped>
.cart-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
  padding: 0.5rem 0;
}
</style>
