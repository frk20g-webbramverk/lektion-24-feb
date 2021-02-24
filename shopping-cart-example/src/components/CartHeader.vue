<template>
  <header class="header">
    <cart v-bind:total="cartTotal"></cart>
  </header>
</template>

<script>
import Cart from './Cart';

export default {
  name: 'cart-header',
  components: {
    Cart
  },
  props: {
    cartTotal: Number
  }
}
</script>

<style>
.header {
  width: 100%;
  height: 80px;
  padding: 1rem;
}
</style>