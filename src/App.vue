<template>
  <div>
    <div id="header">
      <Search v-on:query-change="querySearch" />
    </div>

    <div id="main-container">
      <h2>List Of Books</h2>
      <TodoAdd v-on:add-todo="addTodo" />
      <Todos v-bind:todoslist="copyTodos" v-on:delete-todo="deleteTodo" />
    </div>
  </div>
</template>

<script>
import Search from "./components/Search";
import Todos from "./components/Todos";
import TodoAdd from "./components/TodoAdd";

export default {
  name: "App",
  components: {
    Todos,
    TodoAdd,
    Search,
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id != id);
      this.copyTodos = [...this.todos];
    },
    addTodo(todo) {
      this.todos.push(todo);
      this.copyTodos = [...this.todos];
    },
    querySearch(query) {
      if (query.trim() === "") {
        this.copyTodos = [...this.todos];
      } else {
        const temp = this.todos.filter((todo) => {
          return todo.title.includes(query);
        });

        this.copyTodos = [...temp];
      }
    },
  },
  data() {
    return {
      todos: [
        {
          id: 0,
          title: "Sol de medianoche",
          completed: false,
        },
        {
          id: 1,
          title: "Caste: The Origins of Our Discontents",
          completed: true,
        },
        {
          id: 2,
          title: "Mi historia",
          completed: false,
        },
        {
          id: 3,
          title: "White Fragility",
          completed: true,
        },
      ],
      copyTodos: [],
    };
  },
  created() {
    this.copyTodos = [...this.todos];
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
#main-container {
  border: solid 1px #ccc;
  width: 600px;
  margin: auto;
}

#header {
  background: white;
}

h2 {
  padding: 0 10px;
}
</style>
