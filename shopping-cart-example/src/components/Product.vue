<template>
  <article class="product">
    <h2>{{ book.title }}</h2>
    <h3>{{ book.author }}</h3>

    <p>{{ book.text }}</p>

    <button v-on:click="addToCart" class="button">Add to cart</button>
  </article>
</template>

<script>
export default {
  name: 'product',
  props: {
    book: Object
  },
  methods: {
    addToCart: function() {
      this.$emit('addToCart', this.book);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.product {
  max-width: 300px;
  background-color: #fffffe;
  text-align: center;
  padding: 1.2rem;
  box-shadow: 0 5px 15px -10px rgba(31, 18, 53, 0.6);
  border-radius: 3px;
  margin: 0 auto;
}

.button {
    background-color: #37AEAB;
    outline: none;
    padding: 1.2rem;
    border: none;
    border-radius: 3px;
    font-size: 1rem;
    font-weight: 700;
    cursor: pointer;
    margin-top: 1rem;
    transition: box-shadow 0.3s;
    color: #ffffff;
}
</style>
