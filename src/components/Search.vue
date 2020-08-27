<template>
  <div>
    <v-row align="center" justify="center">
      <v-spacer></v-spacer>
      <v-col cols="12" md="4" align="center">
        <v-text-field label="Search Books" v-model="query" v-on:input="$emit('query-change', query)"></v-text-field>
      </v-col>
      <v-spacer></v-spacer>
    </v-row>
  </div>
</template>

<script>
export default {
  name: "Search",
  data() {
    return {
      query: "",
    };
  },
};
</script>
