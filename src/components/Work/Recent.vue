<script setup>
import Typography from "components/Typography/Typography.vue";
</script>

<template>
  <section class="recent-work-container">
    <Typography class="recent-work-header cursive-font" variant="h1">
      What I've been working on.
    </Typography>
    <Typography class="recent-work-text" variant="h4">
      Here's some of my recent work. To see more visit me on
      <a
        class="recent-work-link"
        href="https://github.com/marc-akbar"
        target="_blank"
        >Github</a
      >.
    </Typography>
  </section>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.recent-work-container {
  margin: 0;
  padding-top: 7rem;
  padding-bottom: 7rem;
  background-color: var(--recent-work-background);
  text-align: center;
}

.recent-work-header {
  margin: 0;
  padding-bottom: 2rem;
  color: var(--recent-work-title);
}

.recent-work-text {
  color: var(--recent-work-text);
}

.recent-work-link {
  color: $custom-teal;
}
</style>
