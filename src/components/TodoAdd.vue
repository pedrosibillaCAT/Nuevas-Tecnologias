<template>
  <div>
    <form @submit="addTodo">
      <v-row align="center" justify="center" >
        <v-spacer></v-spacer>
        <v-col cols="12" md="11" align="center">
          <v-text-field label="Add" v-model="title"></v-text-field>
        </v-col>
        <v-spacer></v-spacer>
      </v-row>
    </form>
  </div>
</template>

<script>
import { uuid } from "vue-uuid";

export default {
  name: "TodoAdd",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();

      const newTodo = {
        id: uuid.v4(),
        title: this.title,
        completed: false,
      };

      this.title = "";
      this.$emit("add-todo", newTodo);
    },
  },
};
</script>