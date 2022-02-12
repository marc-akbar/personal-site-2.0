<script setup>
import Navigation from "components/Navigation.vue";
import Head from "components/Head.vue";
</script>

<template>
  <div class="wrapper night">
    <Head />
    <Navigation />
    <RouterView />
  </div>
</template>

<style lang="scss">
@import "assets/palette.scss";

body {
  margin: 0 !important;
}

p {
  letter-spacing: 0.02857rem;
}

.wrapper {
  min-height: 100vh;
  position: relative;
  overflow-x: hidden;
  overflow-y: hidden;
  background-color: var(--background);
  transition: color 0.5s ease, background-color 0.5s ease;
}
</style>
