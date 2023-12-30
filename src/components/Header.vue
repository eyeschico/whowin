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
  font-weight: 500;
  text-transform: capitalize;
  font-size: 8rem;
  padding: 0;
  margin: 0;
  padding-top: 1rem;
}

.logo {
  text-align: center;
}

@media (min-width: 1024px) {
  .logo h1 {
    text-align: left;
  }
}
</style>
