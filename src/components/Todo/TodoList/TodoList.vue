<template>
  <ul>
    <TodoItem
      v-for="(todo, indexTodo) of todos"
      :todo="todo"
      :key="todo"
      :indexTodo="indexTodo"
      v-on:remove-todo-item="removeTODO"
    />
  </ul>
</template>

<script>
import TodoItem from "./TodoItem/TodoItem";
export default {
  props: ["todos"],
  components: {
    TodoItem,
  },
  methods: {
    removeTODO(id) {
      this.$emit("remove-todo", id);
    },
  },
};
</script>

<style lang="scss" scoped>
ul {
  width: 37%;
}
</style>
