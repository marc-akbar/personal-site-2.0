<script setup>
const props = defineProps({
  variant: String,
  theme: String,
});
</script>

<template>
  <h1 v-if="variant === 'h1'" class="root">
    <span :class="theme === 'nes' && nes - text"><slot /></span>
  </h1>
  <h2 v-else-if="variant === 'h2'" class="root">
    <span :class="theme === 'nes' && nes - text"><slot /></span>
  </h2>
  <h3 v-else-if="variant === 'h3'" class="root">
    <span :class="theme === 'nes' && nes - text"><slot /></span>
  </h3>
  <h4 v-else-if="variant === 'h4'" class="root">
    <span :class="theme === 'nes' && nes - text"><slot /></span>
  </h4>
  <h5 v-else-if="variant === 'h5'" class="root">
    <span :class="theme === 'nes' && nes - text"><slot /></span>
  </h5>
  <h6 v-else-if="variant === 'h6'" class="root">
    <span :class="theme === 'nes' && nes - text"><slot /></span>
  </h6>
  <p v-else-if="variant === 'p'" class="root">
    <span :class="theme === 'nes' && nes - text"><slot /></span>
  </p>
  <div v-else class="root">
    <span :class="theme === 'nes' && nes - text"><slot /></span>
  </div>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.root {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    Oxygen-Sans, Ubuntu, Cantarell, "Helvetica Neue", sans-serif;
}
</style>
