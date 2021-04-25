<template>
  <v-app>
    <v-app-bar
      app
      color="green darken-2"
      dark
    >
    <h1>Todo App</h1>
    </v-app-bar>
    <v-main>
      <Todo/>
    </v-main>
  </v-app>
</template>

<script>
import Todo from './components/Todo';

export default {
  name: 'App',

  components: {
    Todo,
  },

  data: () => ({
    //
  }),
};
</script>
