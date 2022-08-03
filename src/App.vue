<!-- eslint-disable no-undef -->
<script setup>
import { RouterLink, RouterView } from "vue-router";
import HelloWorld from "./components/HelloWorld.vue";

</script>

<template>
  <header>
    <div class="wrapper">
      <HelloWorld msg="That's News To Me" />

      <nav class="btnHover">
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<script>
// eslint-disable-next-line no-undef
// app.mount("#app");
</script>

<style>
header {
  line-height: 1.5;
  max-height: 100vh;
  color: rgb(3, 30, 70);
}

nav {
  width: 100%;
  font-size: 1.5em;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  /* color: var(--color-text); */
  color: rgb(88, 15, 51);

  /* color: #013848; */
}

nav a.router-link-exact-active:hover {
  /* background-color: transparent; */
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  /* border-left: 3px solid var(--color-border); */
  border-left: 3px solid rgb(255, 255, 255);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
