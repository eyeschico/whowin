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
  font-size: 4rem;
  padding: 0;
  margin: 0;
  padding-top: 2rem;
  cursor: default;
}

.logo {
  text-align: center;
}

@media (min-width: 1024px) {
}
</style>
