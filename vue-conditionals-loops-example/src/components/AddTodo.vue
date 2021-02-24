<template>
  <section>
      <input type="text" placeholder="Lägg till todo" v-model="todo">
      <button v-on:click="addTodo">Lägg till</button>
  </section>
</template>

<script>
export default {
    name: 'add-todo',
    data: function() {
        return {
            todo: ''
        }
    },
    methods: {
        addTodo: function() {
            this.$emit('addTodo', this.todo);
        }
    }
}
</script>

<style>

</style>