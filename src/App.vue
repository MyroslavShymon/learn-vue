<template>
  <div id="app">
    <router-view />
    <main class="todo">
      <h1 class="todo__title">TODO application</h1>
      <TodoList v-bind:todos="todos" />
    </main>
  </div>
</template>

<script>
import TodoList from "@/components/TodoList";
export default {
  components: {
    TodoList,
  },
  data() {
    return {
      todos: [
        { id: 1, title: "Learn Vue3", completed: false },
        { id: 2, title: "Make cool project", completed: false },
        { id: 3, title: "Drink coke", completed: false },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.todo {
  display: flex;
  width: 100%;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  color: #1b1612;
  &__title {
    font-size: 37px;
    margin: 20px;
    font-weight: bold;
    color: #f8a73f;
  }
}
</style>
