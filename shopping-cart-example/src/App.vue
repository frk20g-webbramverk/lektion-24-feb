<template>
  <div id="app">
    <cart-header v-bind:cartTotal="cart.length"></cart-header>
    <product v-for="product in products" 
      v-bind:key="product.id" v-bind:book="product"
      v-on:addToCart="addToCart"></product>
  </div>
</template>

<script>
import Product from './components/Product';
import CartHeader from './components/CartHeader';

export default {
  name: 'App',
  components: {
    Product,
    CartHeader
  },
  data: function() {
    return {
      products: [
        { id: 1, title: 'A Sign of Four', author: 'Sir Arthur Conan Doyle', text: 'Om Sherlock' },
        { id: 2, title: 'A Study in Scarlet', author: 'Sir Arthur Conan Doyle', text: 'Om Sherlock' },
        { id: 3, title: 'Baskervilles Hound', author: 'Sir Arthur Conan Doyle', text: 'Om Sherlock' },
        { id: 4, title: 'The Adventures of Sherlock Holmes', author: 'Sir Arthur Conan Doyle', text: 'Om Sherlock' }
      ],
      cart: []
    }
  },
  methods: {
    addToCart: function(book) {
      this.cart.push(book);
    }
  }
}
</script>

<style>
body {
  width: 100vw;
  height: 100vh;
  margin: 0;
  padding: 0;
  background-color: #231F42;
  display: flex;
  justify-content: center;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 60px;
}
</style>
