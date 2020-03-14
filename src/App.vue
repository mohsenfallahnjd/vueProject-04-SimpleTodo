<template>
  <div id="app">
    <Header @createTodo="createTodo" />
    <Todos :todos="todos" @removeTodo="removeTodo" />
  </div>
</template>

<script>
import Header from "./components/Header";
import Todos from "./components/Todos";

let todos = [
  {
    id: 1,
    name: "Record Video",
    done: false
  },
  {
    id: 2,
    name: "upload Video",
    done: false
  },
  {
    id: 3,
    name: "parttay",
    done: false
  },
  {
    id: 4,
    name: "Debug",
    done: false
  },
  {
    id: 5,
    name: "More Debug",
    done: false
  }
];

export default {
  name: "App",
  components: {
    Header,
    Todos
  },
  data: () => {
    return {
      todos: todos
    };
  },
  methods: {
    createTodo(todo) {
      const todoId =
        this.todos.length > 0 ? this.todos[this.todos.length - 1].id + 1 : 1;

      const newTodo = {
        id: todoId,
        name: todo,
        done: false
      };

      this.todos.push(newTodo);
    },
    removeTodo(id) {
      this.todos = this.todos.filter(todo => todo.id != id);
    }
  }
};
</script>

<style lang="scss">
body {
  margin: 0;
  padding: 0;
  background-color: #f3f3f3;

  font-family: Arial, Helvetica, sans-serif;
}
</style>
