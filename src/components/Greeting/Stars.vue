<script setup>
import { ref, onMounted } from "vue";
import { gsap } from "gsap";

function populateStars() {
  // Star population in scene
  var width = $("#scene").width();
  var sceneHeight = $("#scene").height();
  var rightBound = width * 0.37; // right boundary for left star population
  var leftBound = width * 0.63; // left boundary for right star population
  var footerHeight = $("#say-hi").height();
  var stars = ["white-star-image", "gold-star-image", "teal-star-image"];

  stars.forEach(populateLeftStars);
  stars.forEach(populateMiddleStars);
  stars.forEach(populateRightStars);
  stars.forEach(populateFooterStars);

  function populateLeftStars(value) {
    for (var i = 0; i < width / 100; i++) {
      // Pad the left by 10px
      var left = Math.floor(Math.random() * (rightBound - 10)) + 10;
      var top =
        Math.floor(Math.random() * (sceneHeight - sceneHeight * 0.3)) +
        sceneHeight * 0.15;
      $(`<div class='${value}'></div>`)
        .appendTo("#scene.night")
        .css({ left: left, top: top });
    }
  }
  function populateMiddleStars(value) {
    for (var i = 0; i < width / 100; i++) {
      // Pad the left and right by 10px
      var left = Math.floor(Math.random() * (width - 25)) + 10;
      var top =
        Math.floor(Math.random() * (sceneHeight - sceneHeight * 0.59)) +
        sceneHeight * 0.5;
      $(`<div class='${value}'></div>`)
        .appendTo("#scene.night")
        .css({ left: left, top: top });
    }
  }
  function populateRightStars(value) {
    for (var i = 0; i < width / 100; i++) {
      // Pad the right by 10px
      var left =
        Math.floor(Math.random() * (width - leftBound - 25)) + leftBound - 25;
      var top =
        Math.floor(Math.random() * (sceneHeight - sceneHeight * 0.3)) +
        sceneHeight * 0.15;
      $(`<div class='${value}'></div>`)
        .appendTo("#scene.night")
        .css({ left: left, top: top });
    }
  }
  function populateFooterStars(value) {
    for (var i = 0; i < width / 100; i++) {
      // Pad the left and right by 10px
      var left = Math.floor(Math.random() * (width - 25)) + 10;
      var top = Math.floor(Math.random() * (footerHeight - 25)) + 25;
      $(`<div class='${value}'></div>`)
        .appendTo("#say-hi")
        .css({ left: left, top: top });
    }
  }
}

function easeInStars() {
  gsap.from([".white-star-image", ".gold-star-image", ".teal-star-image"], {
    opacity: 0,
    ease: "power3.in",
    duration: 1,
  });
}

function rotateStars() {
  gsap.from(".gold-star-image", {
    repeat: -1,
    rotation: -360,
    duration: 5,
    ease: "none",
  });
  gsap.from(".teal-star-image", {
    repeat: -1,
    rotation: -360,
    duration: 10,
    ease: "none",
  });
}

// onMounted(() => {
//   easeInClouds();
//   raiseClouds();
// });
</script>

<template>
  <div class="stars" />
</template>

<style lang="scss">
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
