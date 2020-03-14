<template>
  <header>
    <input
      type="text"
      name="todoInput"
      v-model="todoValue"
      placeholder="Add task"
    />
    <button class="submit" @click="createTodo">
      +
    </button>
  </header>
</template>

<script>
export default {
  name: "Header",
  data: () => {
    return {
      todoValue: ""
    };
  },
  methods: {
    createTodo() {
      if (this.todoValue != "") {
        this.$emit("createTodo", this.todoValue);
        this.todoValue = "";
      }
    }
  }
};
</script>

<style lang="scss" scoped>
header {
  display: flex;

  input {
    flex: 1;
    height: 50px;
    box-sizing: border-box;
    font-size: 20px;
    text-indent: 15px;
  }
  .submit {
    width: 50px;
    height: 50px;
    font-size: 28px;
    cursor: pointer;
    color: #171717;
    background-color: #ffce00;
    border: none;
    outline: none;
    font-weight: 700;
    line-height: 1;

    &:hover {
      background-color: lighten($color: #ffce00, $amount: 10);
    }
    &:active {
      background-color: darken($color: #ffce00, $amount: 5);
    }
  }
}
</style>
