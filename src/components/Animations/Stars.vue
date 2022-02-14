<script setup>
import { ref, watchEffect } from "vue";
import { gsap } from "gsap";

const props = defineProps({
  scene: String,
});

const starColors = ["white-star", "gold-star", "teal-star"];
const starCoordinates = [];

function populateStars() {
  // Star population in scene
  var sceneWidth = scene.offsetWidth;
  var sceneHeight = scene.clientHeight;
  var rBound = sceneWidth * 0.37; // right boundary for left star population
  var lBound = sceneWidth * 0.63; // left boundary for right star population

  starColors.map((starColor) => {
    for (var i = 0; i < sceneWidth / 100; i++) {
      {
        // Pad the left by 10px
        var left = Math.floor(Math.random() * (rBound - 10)) + 10;
        var top =
          Math.floor(Math.random() * (sceneHeight - sceneHeight * 0.3)) +
          sceneHeight * 0.015;
        starCoordinates.push({
          color: starColor,
          left: `${left}px`,
          top: `${top}px`,
        });
      }

      {
        // Pad the left and right by 10px
        var left = Math.floor(Math.random() * (sceneWidth - 25)) + 10;
        var top =
          Math.floor(Math.random() * (sceneHeight - sceneHeight * 0.59)) +
          sceneHeight * 0.3;
        starCoordinates.push({
          color: starColor,
          left: `${left}px`,
          top: `${top}px`,
        });
      }

      {
        // Pad the right by 10px
        var left =
          Math.floor(Math.random() * (sceneWidth - lBound - 25)) + lBound - 25;
        var top =
          Math.floor(Math.random() * (sceneHeight - sceneHeight * 0.3)) +
          sceneHeight * 0.015;
        starCoordinates.push({
          color: starColor,
          left: `${left}px`,
          top: `${top}px`,
        });
      }
    }
  });
}

function easeInStars() {
  gsap.from([".white-star", ".gold-star", ".teal-star"], {
    opacity: 0,
    ease: "power3.in",
    duration: 1,
  });
}

function rotateStars() {
  gsap.from(".gold-star", {
    repeat: -1,
    rotation: -360,
    duration: 5,
    ease: "none",
  });
  gsap.from(".teal-star", {
    repeat: -1,
    rotation: 360,
    duration: 10,
    ease: "none",
  });
}

watchEffect(async () => {
  await populateStars();
  easeInStars();
  rotateStars();
});
</script>

<template>
  <div>
    <div
      v-if="starCoordinates.length"
      v-for="c in starCoordinates"
      :class="c.color"
      :style="{ top: c.top, left: c.left }"
    />
  </div>
</template>

<style lang="scss">
.white-star {
  content: url("images/scenes/white-star.png");
  position: absolute;
  height: 4px;
  z-index: 1;
}

.gold-star {
  content: url("images/scenes/gold-star.png");
  position: absolute;
  height: 8px;
  z-index: 1;
}

.teal-star {
  content: url("images/scenes/teal-star.png");
  position: absolute;
  height: 15px;
  z-index: 1;
}
</style>
