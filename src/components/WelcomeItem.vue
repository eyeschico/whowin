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
  font-size: 2rem;
}

@media (min-width: 1024px) {
}
</style>
