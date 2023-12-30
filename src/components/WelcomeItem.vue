<template>
  <div class="item">
    <h3>
      <slot name="heading"></slot>
    </h3>
  </div>
</template>

<style scoped>
.item {
  margin-top: 2rem;
}

h3 {
  font-size: 3rem;
  margin-bottom: 0.4rem;
  text-transform: uppercase;
}

@media (min-width: 1024px) {
}
</style>
