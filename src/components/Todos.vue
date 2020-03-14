<template>
  <section id="todos">
    <div class="todo" v-for="todo in todos" :key="todo.id">
      <input type="checkbox" name="done" v-if="todo.done" checked />
      <input type="checkbox" name="done" v-else />
      <label for="done">
        {{ todo.name }}
      </label>

      <button class="remove" @click="removeTodo(todo.id)">Remove</button>
    </div>
  </section>
</template>

<script>
export default {
  name: "todos",
  props: { todos: Array },
  methods: {
    removeTodo(id) {
      this.$emit("removeTodo", id);
    }
  }
};
</script>

<style lang="scss" scoped>
#todos {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  width: 100%;

  .todo {
    width: 24%;
    background-color: #fff;
    margin: 15px;
    padding: 15px;

    display: flex;

    label {
      flex: 1;
    }
  }
}
</style>
