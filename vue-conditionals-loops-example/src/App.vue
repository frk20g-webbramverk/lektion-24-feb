<template>
  <div id="app">
    <section>
      <todo-counter v-bind:count="counter"></todo-counter>
      <ul>
        <todo-item v-for="todo in todos" v-bind:key="todo.id" 
          v-bind:task="todo.task" v-bind:done="todo.done" v-on:done="handleUpdate"></todo-item>
      </ul>
      <button v-on:click="showAddTodo">Lägg till todo</button>
      <add-todo v-if="addTodo" v-on:addTodo="addNewTodo"></add-todo>
    </section>
  </div>
</template>

<script>
import TodoItem from './components/TodoItem';
import TodoCounter from './components/TodoCounter';
import AddTodo from './components/AddTodo';

export default {
  name: 'App',
  components: {
    TodoItem,
    TodoCounter,
    AddTodo
  },
  data: function() {
    return {
      counter: 0,
      todos: [
        { id: 0, task: 'Köp kaffe', done: false },
        { id: 1, task: 'Köp kaka', done: false },
        { id: 2, task: 'Brygg kaffe', done: false },
        { id: 3, task: 'Drick kaffe', done: false }
      ],
      addTodo: false
    }
  },
  methods: {
    handleUpdate: function() {
      this.counter = this.counter + 1;
    },
    addNewTodo: function(todo) {
      console.log('New todo: ', todo);
      const calculateId = this.todos.length;
      this.todos.push({ id: calculateId, task: todo, done: false })
    },
    showAddTodo: function() {
      //Inverterar värdet i egenskapen så true blir false och vice versa
      this.addTodo = !this.addTodo;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
