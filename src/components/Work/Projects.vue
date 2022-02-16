<script setup>
import { projectData } from "components/Work/projectData.js";
import WiggleButton from "components/Buttons/WiggleButton.vue";
</script>

<template>
  <div class="wrapper">
    <div class="container" v-for="(p, index) in projectData">
      <img
        class="image"
        :style="[index & 1 ? { order: 3 } : { order: 1 }]"
        :src="p.image.source"
        :alt="p.image.description"
      />

      <div class="gap" />

      <div :style="[index & 1 ? { order: 1 } : { order: 3 }]">
        <h4 class="title">{{ p.title }}</h4>
        <h6 class="subtitle">{{ p.subtitle }}</h6>
        <p class="description">{{ p.description }}</p>
        <div class="link-wrapper">
          <a v-for="l in p.links" class="link" target="_blank" :href="l.url">
            <WiggleButton class="button" :label="l.label" />
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.wrapper {
  background-color: var(--eb-background);
}

.container {
  max-width: 1280px;
  margin: 0 auto;
  padding: 7rem;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.gap {
  padding-left: 5rem;
  order: 2;
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

.link-wrapper {
  display: flex;
}

.link {
  text-decoration: none;
}

.button {
  font-weight: bold;
  margin-right: 0.5rem;
  background-color: var(--eb-btn);
  color: var(--eb-btn-text);
  padding: 1rem;
}
</style>
