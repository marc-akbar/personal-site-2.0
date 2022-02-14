<script setup>
import { RouterLink } from "vue-router";
import Toggle from "components/Navigation/Toggle.vue";
import Hello from "components/Animations/Hello.vue";

const props = defineProps({
  darkMode: Boolean,
  toggleTime: Function,
});
</script>

<template>
  <nav class="nav-root">
    <div class="nav-container">
      <div class="nav-wrapper">
        <Toggle :darkMode="darkMode" @click="toggleTime" />

        <div class="nav-links">
          <RouterLink class="nav-link" to="/">home</RouterLink>
          <RouterLink class="nav-link" to="/about">about</RouterLink>
        </div>
      </div>
    </div>
  </nav>
</template>

<style lang="scss">
@import "assets/palette.scss";

.nav-root {
  background-color: var(--nav-background);
}

.nav-container {
  margin: 0 auto;
  padding: 0.5rem;
  max-width: 1280px;
}

.nav-wrapper {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.nav-links {
  padding-right: 1rem;
}

.nav-link {
  display: inline-block;
  margin-top: 0.75rem;
  padding-left: 2rem;
  padding-right: 2rem;
  font-family: "Baloo Tammudu 2", cursive, sans-serif;
  font-weight: 600;
  font-size: 1.25rem;
  text-decoration: none;
  text-transform: uppercase;
  transition: color 0.5s ease, background-color 0.5s ease;
  color: var(--nav-btn);

  &:hover {
    background-color: inherit !important;
    color: $custom-teal !important;
  }
}
</style>
