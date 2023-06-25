<template>
  <div>
    <ul>
      <TodoItem
        v-for="(todo, i) in todos"
        v-bind:todo="todo"
        v-bind:index="i"
        v-on:remove-todo="removeTodo"
      />
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue';
export default {
  props: ['todos'],
  name: 'TodoList',
  components: { TodoItem },
  methods: {
    removeTodo(id) {
      console.log(id);
      this.$emit('remove-todo', id);
    },
  },
};
</script>

<style scoped>
/*Scoped - cтили внутри компонента */

ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
</style>
