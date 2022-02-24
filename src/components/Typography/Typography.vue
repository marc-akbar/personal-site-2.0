<script setup>
const props = defineProps({
  variant: String,
});
</script>

<template>
  <h1 v-if="variant === 'h1'" class="typography-root">
    <span class="nes-text"><slot /></span>
  </h1>
  <h2 v-else-if="variant === 'h2'" class="typography-root">
    <span class="nes-text"><slot /></span>
  </h2>
  <h3 v-else-if="variant === 'h3'" class="typography-root">
    <span class="nes-text"><slot /></span>
  </h3>
  <h4 v-else-if="variant === 'h4'" class="typography-root">
    <span class="nes-text"><slot /></span>
  </h4>
  <h5 v-else-if="variant === 'h5'" class="typography-root">
    <span class="nes-text"><slot /></span>
  </h5>
  <h6 v-else-if="variant === 'h6'" class="typography-root">
    <span class="nes-text"><slot /></span>
  </h6>
  <p v-else class="typography-root">
    <span class="nes-text"><slot /></span>
  </p>
</template>

<style lang="scss" scoped>
.typography-root {
  margin: 0;
  font-weight: normal;
  font-family: inherit, -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen-Sans, Ubuntu, Cantarell, "Helvetica Neue", sans-serif;
}
</style>
