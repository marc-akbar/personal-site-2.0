<script setup>
import FillIconButton from "components/Buttons/FillIconButton.vue";
</script>

<template>
  <div class="social">
    <FillIconButton href="https://github.com/marc-akbar" class="social-item">
      <img class="social-image" src="public/images/logos/GitHub-logo.png" />
    </FillIconButton>

    <FillIconButton href="https://www.linkedin.com/in/marc-akbar/" class="social-item">
      <img class="social-image" src="public/images/logos/LinkedIn-logo.png" />
    </FillIconButton>

    <FillIconButton href="https://www.instagram.com/snack_bar13/" class="social-item">
      <img class="social-image" src="public/images/logos/Instagram-logo.png" />
    </FillIconButton>
  </div>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.social {
  padding: 1rem 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

.social-item {
  height: 2.25rem;
  padding: 0 1.5rem;
  background-color: var(--logo-filter);
}

.social-image {
  height: 100%;
}
</style>
