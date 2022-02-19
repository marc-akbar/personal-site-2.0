<script setup>
import HelloSVG from "components/Animations/HelloSVG.vue";
</script>

<template>
  <div class="welcome-wrapper">
    <div class="welcome-title"><HelloSVG /></div>
    <div class="welcome-text">I'm Marc, a web-based developer.</div>
  </div>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.welcome-wrapper {
  margin-bottom: 7vw;
}

.welcome-title {
  position: relative;
  margin-bottom: 4vw;
  z-index: 2;
}

.welcome-text {
  position: relative;
  font-family: "Baloo Tammudu 2", cursive, sans-serif;
  font-size: 2.25rem;
  z-index: 2;
  color: var(--greeting-text);
}
</style>
