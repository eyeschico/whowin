<script setup>
import { RouterLink } from "vue-router";
import Header from "./components/Header.vue";
</script>

<template>
  <header>
    <div class="wrapper">
      <Header title="WHO WIN" />

      <nav>
        <RouterLink to="/">HOME</RouterLink>
        <RouterLink to="/start">START</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>
header {
  max-height: 100vh;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
  margin-right: 0;
}

nav a {
  display: inline-block;
  font-size: 2rem;
  padding: 0.5rem;
  padding-top: 1rem;
  padding-right: 1.5rem;
  padding-left: 1.5rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    margin-right: 0.8rem;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-right: -2rem;
    font-size: 1rem;
  }
}
</style>
