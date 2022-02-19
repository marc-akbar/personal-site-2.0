<template>
  <section class="recent-work-container">
    <h2 class="recent-work-header">What I've been working on.</h2>
    <p class="recent-work-text">
      Here's some of my recent work. To see more visit me on
      <a
        class="recent-work-link"
        href="https://github.com/marc-akbar"
        target="_blank"
        >Github</a
      >.
    </p>
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
  font-family: "Satisfy", cursive, sans-serif;
  font-size: 3.4rem;
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
