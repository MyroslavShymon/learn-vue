<template>
  <ul>
    <TodoItem v-for="todo of todos" :todo="todo" :key="todo" />
  </ul>
</template>

<script>
import TodoItem from "@/components/TodoItem";
export default {
  props: ["todos"],
  components: {
    TodoItem,
  },
};
</script>

<style lang="scss" scoped>
ul {
  width: 37%;
}
</style>
