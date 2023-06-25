<template>
  <div class="todo__item" v-bind:class="{ done: todo.completed }">
    <!-- Динамический класс -->
    <input type="checkbox" v-on:change="todo.completed = !todo.completed" />
    <li>
      <strong>{{ index }}</strong
      >{{ todo.title }}
    </li>
    <button v-on:click="$emit('remove-todo', todo.id)">&times;</button>
  </div>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
    index: Number,
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
.todo__item {
  display: flex;
}
.done {
  text-decoration: line-through;
}
</style>
