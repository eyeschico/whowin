<script setup>
defineProps({
  title: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="logo">
    <h1 class="yellow">{{ title }}</h1>
  </div>
</template>

<style scoped>
h1 {
  text-transform: capitalize;
  font-size: 5rem;
  padding: 0;
  margin: 0;
  padding-top: 2rem;
  padding-right: 2.5rem;
}

.logo {
  text-align: center;
}

@media (min-width: 1024px) {
}
</style>
