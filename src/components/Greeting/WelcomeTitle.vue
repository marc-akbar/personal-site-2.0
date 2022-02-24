<script setup>
import HelloSVG from "components/Animations/HelloSVG.vue";
import Typography from "components/Typography/Typography.vue";
</script>

<template>
  <div class="welcome-wrapper">
    <div class="welcome-title"><HelloSVG /></div>
    <Typography class="welcome-text bamboo-font" variant="h2"
      >I'm Marc, a web-based developer.
    </Typography>
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
  z-index: 2;
  color: var(--greeting-text);
}
</style>
