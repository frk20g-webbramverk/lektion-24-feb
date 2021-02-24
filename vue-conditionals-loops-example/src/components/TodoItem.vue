<template>
  <li v-on:click="update">{{ task }}</li>
</template>

<script>
export default {
    name: 'todo-item',
    props: {
        task: String,
        done: Boolean
    },
    methods: {
        update: function() {
            this.$emit('done', this.task);
        }
    }
}
</script>

<style>

</style>