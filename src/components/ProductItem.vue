<template>
  <li>
    {{ product.name }} - Rp {{ product.price }}
    <button @click="addToCart(product)">+ Keranjang</button>
    <button @click="remove(product.id)">Hapus</button>
  </li>
</template>

<script setup>
import { useProductStore } from '../stores/productStore'
import { useCartStore } from '../stores/cartStore'

const props = defineProps({ product: Object })

const productStore = useProductStore()
const cartStore = useCartStore()

function addToCart(product) {
  cartStore.addToCart(product)
}

function remove(id) {
  productStore.removeProduct(id)
}
</script>
