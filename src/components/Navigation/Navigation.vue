<script setup>
import { RouterLink } from "vue-router";
import Toggle from "components/Navigation/Toggle.vue";

const props = defineProps({
  darkMode: Boolean,
  toggleTime: Function,
});
</script>

<template>
  <nav class="nav-root">
    <div class="nav-container">
      <div class="nav-wrapper">
        <div class="nav-toggle">
          <Toggle :darkMode="props.darkMode" @click="props.toggleTime" />
        </div>

        <div>
          <RouterLink class="nav-link" to="/">home</RouterLink>
          <RouterLink class="nav-link" to="/about">about</RouterLink>
        </div>
      </div>
    </div>
  </nav>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.nav-root {
  background-color: var(--nav-background);
}

.nav-container {
  height: 64px;
  padding: 0.5rem;
}

.nav-wrapper {
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.nav-toggle {
  height: 100%;
  position: relative;
}

.nav-link {
  display: inline-block;
  margin-top: 0.75rem;
  padding-left: 2rem;
  padding-right: 2rem;
  font-family: "Baloo Tammudu 2", cursive, sans-serif;
  font-weight: 600;
  font-size: 1.25rem;
  text-transform: uppercase;
  transition: color 0.5s ease, background-color 0.5s ease;
  color: var(--nav-btn);

  &:hover {
    background-color: inherit !important;
    color: $custom-teal !important;
  }
}
</style>
