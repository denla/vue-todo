<template>
  <h1>Todo List</h1>
  <AddTodo @add-todo="addTodo" />
  <TodoList v-bind:todos="todos" @remove-todo="removeTodo" />
</template>

<script>
import TodoList from './components/TodoList.vue';
import AddTodo from './components/AddTodo.vue';
export default {
  name: 'App',
  components: { TodoList, AddTodo },
  data() {
    return {
      todos: [
        { id: 1, title: 'Купить хлеб', completed: false },
        { id: 2, title: 'Купить огурцы', completed: false },
        { id: 3, title: 'Купить пиво', completed: false },
      ],
    };
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter((item) => item.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    },
  },
};
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
