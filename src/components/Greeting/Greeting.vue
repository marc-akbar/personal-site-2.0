<script setup>
import HandwritingAnimation from "components/Greeting/HandwritingAnimation.vue";
import Particles from "components/Greeting/Particles.vue";
import Clouds from "components/Greeting/Clouds.vue";
</script>

<template>
  <div id="greeting-scene">
    <div id="scene" class="">
      <Clouds />
      <Particles />

      <div class="container">
        <div class="greeting-heading">
          <div class="greeting-title"><HandwritingAnimation /></div>
          <div class="greeting-text">I'm Marc, a web-based developer.</div>
        </div>
        <img
          class="mountain-image"
          src="images/scenes/mountain-range.png"
          alt="mountain range graphic"
        />
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@import "assets/palette.scss";

#scene {
  position: relative;
  z-index: 0;
  background-color: var(--scene-background);
}

.container {
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
  & svg {
    max-width: 90%;
  }
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

.white-star-image {
  content: url("images/scenes/white-star.png");
  position: absolute;
  height: 4px;
  z-index: 1;
}

.gold-star-image {
  content: url("images/scenes/gold-star.png");
  position: absolute;
  height: 8px;
  z-index: 1;
}

.teal-star-image {
  content: url("images/scenes/teal-star.png");
  position: absolute;
  height: 15px;
  z-index: 1;
}
</style>