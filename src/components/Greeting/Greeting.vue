<script setup>
import { ref, onMounted } from "vue";
import { gsap } from "gsap";

import Hello from "components/Animations/Hello.vue";
import Clouds from "components/Animations/Clouds.vue";
import Stars from "components/Animations/Stars.vue";
import Particles from "components/Greeting/Particles.vue";

const props = defineProps({
  darkMode: Boolean,
});

const timeline = gsap.timeline();

onMounted(async () => {
  await populateScene();
});

function populateScene() {
  timeline
    .from(".greeting-text", {
      opacity: 0,
      ease: "power2.in",
      duration: 1,
      delay: 2,
    })
    .from([".mountain-image"], {
      opacity: 0,
      ease: "none",
      duration: 1,
    })
    .addLabel("runScene", "-=1");
}
</script>

<template>
  <div class="greeting-scene">
    <Stars v-if="darkMode" />
    <Clouds v-else />
    <Particles />

    <div class="greeting-container">
      <div class="greeting-heading">
        <div class="greeting-title"><Hello /></div>
        <div class="greeting-text">I'm Marc, a web-based developer.</div>
      </div>
      <img
        class="mountain-image"
        src="images/scenes/mountain-range.png"
        alt="mountain range graphic"
      />
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.greeting-scene {
  position: relative;
  z-index: 0;
  background-color: var(--scene-background);
}

.greeting-container {
  margin: 0 auto;
  max-width: 1280px;
}

.greeting-heading {
  position: relative;
  text-align: center;
  margin-bottom: 7vw;
  z-index: 2;
}

.greeting-title {
  position: relative;
  margin-bottom: 4vw;
  z-index: 2;
}

.greeting-text {
  position: relative;
  font-family: "Baloo Tammudu 2", cursive, sans-serif;
  font-size: 2.25rem;
  z-index: 2;
  color: var(--greeting-text);
}

.mountain-image {
  position: relative;
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 900px;
  max-width: 100%;
  bottom: 0;
  z-index: 2;
}
</style>
