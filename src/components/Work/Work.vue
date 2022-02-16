<script setup>
import Recent from "components/Work/Recent.vue";
</script>

<template>
  <div class="work-container">
    <section class="work-section recent-work">
      <Recent />
    </section>
  </div>
</template>

<style lang="scss">
@import "assets/palette.scss";

.work-section {
  margin: 0;
  padding-top: 7rem;
  padding-bottom: 7rem;
}

.recent-work {
  background-color: var(--recent-work-background);
  text-align: center;
}
</style>
