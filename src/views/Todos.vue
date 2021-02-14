<template>
  <main class="todo">
    <h2 class="todo__title">TODOS</h2>
    <router-link to="/">home</router-link>
    <AddTodo @add-todo="AddTodo" v-bind:todos="todos" />
    <Loader v-if="loading" />
    <TodoList
      v-bind:todos="todos"
      @remove-todo="removeTODO"
      v-else-if="todos.length"
    />
    <p v-else>No todos</p>
  </main>
</template>

<script>
import TodoList from "@/components/Todo/TodoList/TodoList";
import AddTodo from "@/components/Todo/AddTodo/AddTodo";
import Loader from "@/components/Loader/Loader";
export default {
  components: {
    TodoList,
    AddTodo,
    Loader,
  },
  mounted() {
    fetch("https://jsonplaceholder.typicode.com/todos")
      .then((response) => response.json())
      .then((json) => {
        (this.todos = json), (this.loading = false);
      });
  },
  methods: {
    removeTODO(id) {
      this.todos = this.todos.filter((t) => t.id != id);
    },
    AddTodo(todo) {
      this.todos.push(todo);
      console.log(this);
    },
  },
  data() {
    return {
      todos: [],
      loading: true,
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
    font-size: 18px;
    margin: 10px;
    font-weight: bold;
    color: #ff9811;
  }
}
</style>
