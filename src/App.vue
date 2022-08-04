<template>
  <header>
    <div class="wrapper">
      <h3>That's News To Me</h3>

      <nav class="btnHover"></nav>
    </div>
  </header>
  <v-app>
    <v-main>
      <v-app-bar>
        <h2>That's News To Me</h2>
        <v-spacer />
        <v-btn-group v-model="toggle_exclusive">
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
