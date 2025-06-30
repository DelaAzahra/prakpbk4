<template>
  <div>
    <h2>Keranjang</h2>
    <p>Total Item: {{ cart.totalItems }}</p>
    <p>Total Harga: Rp {{ cart.totalPrice }}</p>
    <ul>
      <li v-for="item in cart.cart" :key="item.id">
        {{ item.name }} x{{ item.qty }} = Rp {{ item.qty * item.price }}
      </li>
    </ul>
  </div>
</template>

<script setup>
import { useCartStore } from '../stores/cartStore'
const cart = useCartStore()
</script>
