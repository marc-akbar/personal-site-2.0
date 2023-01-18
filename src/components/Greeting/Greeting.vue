<script setup>
import { ref, onMounted } from "vue";
import { gsap } from "gsap";

import WelcomeTitle from "components/Greeting/WelcomeTitle.vue";
import AboutTitle from "components/Greeting/AboutTitle.vue";
import Clouds from "components/Animations/Clouds.vue";
import Stars from "components/Animations/Stars.vue";
import Particles from "components/Greeting/Particles.vue";

const props = defineProps({
  darkMode: Boolean,
  title: String,
});

onMounted(async () => {
  await populateScene();
});

function populateScene() {
  const timeline = gsap.timeline();

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
    <Stars v-if="props.darkMode" />
    <Clouds v-else />
    <Particles />

    <div class="container">
      <div class="greeting-heading">
        <WelcomeTitle v-if="props.title === 'welcome'" />
        <AboutTitle v-if="props.title === 'about'" />
      </div>
      <img
        class="mountain-image"
        src="public/images/scenes/mountain-range.png"
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

.greeting-heading {
  position: relative;
  text-align: center;
  z-index: 2;
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
