<template>
  <li class="todo__item">
    <div class="todo__wrap">
      <input
        class="todo_checkbox"
        type="checkbox"
        v-on:change="
          {
            todo.completed = !todo.completed;
          }
        "
      />
      <div class="todo__id">{{ ` ${indexTodo + 1} ` }}</div>
      <div
        class="todo__text"
        v-bind:class="{ todo__text_active: todo.completed }"
      >
        {{ ` ${todo.title} ` }}
      </div>
    </div>
    <button
      class="button todo__btn"
      v-on:click="$emit('remove-todo-item', todo.id)"
    >
      &times;
    </button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
    indexTodo: Number,
  },
};
</script>

<style lang="scss" scoped>
@import "./TodoItem.scss";
</style>
