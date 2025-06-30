// src/stores/cartStore.js
import { defineStore } from 'pinia'

export const useCartStore = defineStore('cart', {
  state: () => ({
    cart: []
  }),
  actions: {
    addToCart(product) {
      const existing = this.cart.find(item => item.id === product.id)
      if (existing) {
        existing.qty++
      } else {
        this.cart.push({ ...product, qty: 1 })
      }
    }
  },
  getters: {
    totalItems: (state) => state.cart.reduce((sum, item) => sum + item.qty, 0),
    totalPrice: (state) => state.cart.reduce((sum, item) => sum + item.qty * item.price, 0)
  }
})
