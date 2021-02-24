<template>
  <article class="cart-wrapper">
    <p class="cart-total">Cart {{ total }}</p>
  </article>
</template>

<script>
export default {
  name: 'cart',
  props: {
    total: Number
  }
}
</script>

<style>
.cart-total {
    width: 25px;
    height: 25px;
    border-radius: 999rem;
    background-color: #fffffe;
    display: flex;
    justify-content: center;
    align-items: center;
}

.cart-wrapper {
    width: 300px;
    background-color: #fffffe;
    position: absolute;
    top: 4rem;
    border: 1px solid #f2f2f2;
    display: flex;
    flex-direction: column;
    align-items: center;
}
</style>