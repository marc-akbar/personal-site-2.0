<template>
  <section class="recent-work-container">
    <div class="recent-work-header">
      <span class="nes-text">What I've been working on.</span>
    </div>
    <div class="recent-work-text nes-text">
      Here's some of my recent work. To see more visit me on
      <a
        class="recent-work-link"
        href="https://github.com/marc-akbar"
        target="_blank"
        >Github</a
      >.
    </div>
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
  font-weight: 400;
  margin: 0;
  padding-bottom: 2rem;
  color: var(--recent-work-title);
}

.recent-work-text {
  letter-spacing: 0.02rem;
  font-size: 1.4rem;
  color: var(--recent-work-text);
}

.recent-work-link {
  color: $custom-teal;
}
</style>
