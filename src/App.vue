<script setup>
import { RouterLink } from "vue-router";
import Header from "./components/Header.vue";
</script>

<template>
  <header>
    <div class="wrapper">
      <Header title="WHO WIN" />

      <nav>
        <RouterLink to="/">home</RouterLink>
        <RouterLink to="/start">start</RouterLink>
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
  font-size: 1rem;
  padding: 0.5rem;
  padding-top: 10px;
  text-shadow: none;
}

@media (min-width: 1024px) {
}
</style>
