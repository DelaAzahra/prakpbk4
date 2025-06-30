// src/stores/productStore.js
import { defineStore } from 'pinia'

export const useProductStore = defineStore('product', {
  state: () => ({
    products: []
  }),
  actions: {
    addProduct(name, price) {
      this.products.push({ id: Date.now(), name, price })
    },
    removeProduct(id) {
      this.products = this.products.filter(p => p.id !== id)
    }
  }
})
