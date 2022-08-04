<template>
  <v-app>
    <v-main>
      <v-app-bar color="primary">
        <h2>That's News To Me</h2>
        <v-spacer />
        <v-btn-group>
          <v-btn prepend-icon="mdi-home" to="/">Home</v-btn>
          <v-btn to="/about">About</v-btn>
        </v-btn-group>
      </v-app-bar>
      <router-view />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "App",

  data: () => ({
    //
  }),
};
</script>
