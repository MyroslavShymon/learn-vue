<template>
  <li class="todo__item">
    <div class="todo__wrap">
      <input class="todo_checkbox" type="checkbox" />
      <div class="todo__text">
        {{ ` ${todo.id} ${todo.title} ${todo.completed} ` }}
      </div>
    </div>
    <button class="button todo__btn">&times;</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
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
  }
  &__text {
    margin: 0 0 0 17px;
  }
}
</style>
