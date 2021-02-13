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
.todo {
  &__item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 13px 20px;
    background: #db5c01;
    border-radius: 20px;
    margin: 20px 0;
    font-weight: bold;
    border: 2px solid #ec731c;
    -webkit-box-shadow: 4px 4px 12px -4px #000000;
    box-shadow: 4px 4px 12px -4px #000000;
  }
  &__btn {
    width: 25px;
    height: 25px;
    border-radius: 50%;
    border: 1px solid;
    font-size: 32px;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  &__wrap {
    display: flex;
    width: calc(100% - 35px);
  }
  &__id {
    margin: 0 5px 0 17px;
  }
  &__text {
    &_active {
      text-decoration: line-through;
    }
  }
}
</style>
