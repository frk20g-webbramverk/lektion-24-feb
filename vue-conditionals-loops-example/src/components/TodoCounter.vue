<template>
  <h3>Du har klarat av {{ count }} saker på din todo-lista</h3>
</template>

<script>
export default {
    name: 'todo-counter',
    props: {
        count: Number
    }
}
</script>

<style>

</style>