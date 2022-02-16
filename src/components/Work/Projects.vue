<script setup>
import { projectData } from "components/Work/projectData.js";

import WiggleButton from "components/Buttons/WiggleButton.vue";
</script>

<template>
  <div class="container" v-for="p in projectData">
    <img class="image" :src="p.image.source" :alt="p.image.description" />

    <div class="gap" />

    <div>
      <h4 class="title">{{ p.title }}</h4>
      <h6 class="subtitle">{{ p.subtitle }}</h6>
      <p class="description">
        {{ p.description }}
      </p>
      <a v-for="l in p.links" class="link" target="_blank" :href="l.url">
        <WiggleButton class="button" :label="l.label" />
      </a>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.container {
  padding: 7rem;
  display: flex;
  justify-content: space-around;
  align-items: center;
  background-color: var(--eb-background);
}

.gap {
  padding-left: 5rem;
}

.image {
  max-width: 60%;
  min-width: 313px;
}

.title {
  margin: 0;
  font-family: "Baloo Tammudu 2", cursive, sans-serif;
  font-size: 2.2rem;
  font-weight: 200;
  color: var(--eb-title);
}

.subtitle {
  margin: 0;
  font-size: 1.1rem;
  font-weight: normal;
  padding-bottom: 1.25rem;
  letter-spacing: 0.0625rem;
  color: var(--eb-subtitle);
}

.description {
  color: var(--eb-text);
  font-size: 1rem;
  font-weight: normal;
}

.link {
  text-decoration: none;
}

.button {
  font-weight: bold;
  background-color: var(--eb-btn);
  color: var(--eb-btn-text);
  padding: 1rem;
}
</style>
