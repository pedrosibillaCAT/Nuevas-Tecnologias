<template>
  <v-row>
    <v-spacer></v-spacer>
    <v-col cols="12" md="6" class="todo" v-bind:class="{completed: todo.completed}">
      <v-row align="center">
        <input
          type="checkbox"
          v-bind:checked="todo.completed ? 'checked': ''"
          v-on:change="checkTodo"
        />
        <v-spacer></v-spacer>
        <h4>{{todo.title}}</h4>
      </v-row>
    </v-col>
    <v-spacer></v-spacer>
    <v-col class="todo-actions">
      <v-btn style="background-color:red; color:white" @click="$emit('delete-todo', todo.id)">Eliminar</v-btn>
    </v-col>
    <v-spacer></v-spacer>
  </v-row>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    checkTodo() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style >
.todo {
  border-bottom: solid 1px #ccc;
  padding: 10px;
}

.todo:not(.completed):hover {
  background-color: #eee;
}

.completed {
  color: #ccc;
  text-decoration: line-through;
}

.completed .todo-body {
  text-decoration: line-through;
}

.todo-body,
.todo-actions {
  display: inline-block;
  vertical-align: top;
}

.todo-actions {
  padding: 0 10px;
  width: 10%;
}
button {
  border: none;
  border-radius: 3px;
  padding: 10px;
  background-color: #ccc;
  color: black;
}
button:hover {
  background-color: #da2020;
  color: white;
}
</style>