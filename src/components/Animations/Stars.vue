<script setup>
import { ref, watch } from "vue";
import { gsap } from "gsap";

const starContainerRef = ref(null);
const starCoordinates = ref([]);
const starColors = ["white-star", "gold-star", "teal-star"];

watch(async () => {
  if (!starContainerRef.value) return;

  // wait for component to render container dimensions properly
  await new Promise((r) => setTimeout(r, 300));
  await populateStars();
  easeInStars();
  rotateStars();
});

function populateStars() {
  // Star population in scene
  const containerWidth = starContainerRef.value.offsetWidth;
  const containerHeight = starContainerRef.value.clientHeight;
  const rBound = containerWidth * 0.37; // right boundary for left star population
  const lBound = containerWidth * 0.63; // left boundary for right star population

  starColors.map((starColor) => {
    for (let i = 0; i < containerWidth / 100; i++) {
      {
        // Pad the left by 10px
        const left = Math.floor(Math.random() * (rBound - 10)) + 10;
        const top =
          Math.floor(
            Math.random() * (containerHeight - containerHeight * 0.3)
          ) +
          containerHeight * 0.015;
        starCoordinates.value.push({
          color: starColor,
          left: `${left}px`,
          top: `${top}px`,
        });
      }

      {
        // Pad the left and right by 10px
        const left = Math.floor(Math.random() * (containerWidth - 25)) + 10;
        const top =
          Math.floor(
            Math.random() * (containerHeight - containerHeight * 0.59)
          ) +
          containerHeight * 0.3;
        starCoordinates.value.push({
          color: starColor,
          left: `${left}px`,
          top: `${top}px`,
        });
      }

      {
        // Pad the right by 10px
        const left =
          Math.floor(Math.random() * (containerWidth - lBound - 25)) +
          lBound -
          25;
        const top =
          Math.floor(
            Math.random() * (containerHeight - containerHeight * 0.3)
          ) +
          containerHeight * 0.015;
        starCoordinates.value.push({
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
</script>

<template>
  <div class="star-container" ref="starContainerRef">
    <div
      v-if="starCoordinates.length"
      v-for="c in starCoordinates"
      :class="c.color"
      :style="{ top: c.top, left: c.left }"
    />
  </div>
</template>

<style lang="scss" scoped>
.star-container {
  position: absolute;
  width: 100%;
  height: 100%;
}

.white-star {
  content: url("public/images/scenes/white-star.png");
  position: absolute;
  height: 4px;
  z-index: 1;
}

.gold-star {
  content: url("public/images/scenes/gold-star.png");
  position: absolute;
  height: 8px;
  z-index: 1;
}

.teal-star {
  content: url("public/images/scenes/teal-star.png");
  position: absolute;
  height: 15px;
  z-index: 1;
}
</style>
