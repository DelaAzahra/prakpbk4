<template>
  <div>
    <input v-model="name" placeholder="Nama Produk" />
    <input v-model.number="price" placeholder="Harga" />
    <button @click="add">Tambah Produk</button>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useProductStore } from '../stores/productStore'

const store = useProductStore()
const name = ref('')
const price = ref(0)

function add() {
  if (name.value && price.value > 0) {
    store.addProduct(name.value, price.value)
    name.value = ''
    price.value = 0
  }
}
</script>
