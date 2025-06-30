<template>
  <div>
    <h1>Toko Online (Pinia)</h1>
    <ProductInput />
    <ul>
      <ProductItem
        v-for="product in productStore.products"
        :key="product.id"
        :product="product"
      />
    </ul>
    <Cart />
  </div>
</template>

<script setup>
import ProductInput from './components/ProductInput.vue'
import ProductItem from './components/ProductItem.vue'
import Cart from './components/Cart.vue'
import { useProductStore } from './stores/productStore'

const productStore = useProductStore()
</script>
