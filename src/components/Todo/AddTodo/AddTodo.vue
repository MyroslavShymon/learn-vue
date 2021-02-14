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
      title: "",
    };
  },
  //props: ["todos"],
  methods: {
    onSubmit() {
      if (this.title.trim()) {
        const newTodo = {
          id: Date.now(),
          title: this.title,
          completed: false,
        };
        //this.todos.push(newTodo);
        console.log(this);
        this.$emit("add-todo", newTodo);
      }

      this.title = "";
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/assets/variables.scss";
@import "./AddTodo.scss";
</style>
