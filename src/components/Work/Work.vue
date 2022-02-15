<template>
  <div class="work-container">
    <section class="recent-work">
      <div class="container">
        <h2>What I've been working on.</h2>
        <p>
          Here's some of my recent work. To see more visit me on
          <a href="https://github.com/marc-akbar" target="_blank">Github</a>.
        </p>
      </div>
    </section>
  </div>
</template>

<style lang="scss">
@import "assets/palette.scss";

.work-container {
  & section {
    margin: 0;
    padding-top: 8rem;
    padding-bottom: 8rem;
  }

  & .btn {
    font-weight: bold;
  }
  & .btn:hover {
    filter: contrast(1.4);
    transition: filter 0.4s ease;
  }
  & .row {
    margin-top: 0;
    margin-bottom: 0;
  }

  & h4 {
    font-family: "Baloo Tammudu 2", cursive, sans-serif;
  }
  & h6 {
    padding-bottom: 1rem;
    letter-spacing: 0.0625rem;
  }

  & img {
    min-width: 313px;
    width: 100%;
  }

  & p {
    font-size: 1.1rem;
    & a {
      color: $custom-teal;
    }
  }
}

.recent-work {
  background-color: var(--recent-work-background);
  text-align: center;

  & h2 {
    font-family: "Satisfy", cursive, sans-serif;
    margin: 0;
    padding-bottom: 2rem;
    color: var(--recent-work-title);
  }

  & p {
    font-size: 1.5rem !important;
    color: var(--recent-work-text);
  }
}
</style>
