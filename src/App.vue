<template>
  <div id="app">
    <Header v-on:createTodo="createTodo"/>
    <Todos :todos="todos"/>
  </div>
</template>

<script>
import Header from "./components/Header";
import Todos from "./components/Todos";

let todos = [
  {
    id: "1",
    name: "Test 1",
    done: false
  },
  {
    id: "2",
    name: "Test 2",
    done: false
  },
  {
    id: "3",
    name: "Test 3",
    done: false
  },
  {
    id: "4",
    name: "Test 4",
    done: false
  },
  {
    id: "5",
    name: "Test 5",
    done: false
  }
];

export default {
  name: "app",
  components: {
    Header,
    Todos
  },
  data: function() {
    return {
      todos: todos
    };
  },
  methods: {
    createTodo: function(todo) {
      let todoObject = {
        id: Math.floor(Math.random() * 1000000),
        name: todo,
        done: false
      };
      todos.push(todoObject);
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
