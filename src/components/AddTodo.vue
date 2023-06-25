<template>
  <form @submit.prevent="onSubmit">
    <input type="text" v-model="title" />
    <button type="submit">Create</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      title: '',
    };
  },
  methods: {
    onSubmit(e) {
      //   e.preventDefault();
      console.log('test', this.title);
      const newTodo = {
        id: Date.now(),
        title: this.title,
        completed: false,
      };

      this.$emit('add-todo', newTodo);
    },
  },
};
</script>
