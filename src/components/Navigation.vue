<script setup>
import { RouterLink, RouterView } from "vue-router";
import Toggle from "@/components/Toggle.vue";
</script>

<template>
  <nav class="nav-wrapper">
    <Toggle />
    <div class="nav-links">
      <RouterLink class="nav-link" to="/">home</RouterLink>
      <RouterLink class="nav-link" to="/about">about</RouterLink>
    </div>
  </nav>
</template>

<style lang="scss">
@import "@/assets/base.scss";

.nav-wrapper {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0.5rem;
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
