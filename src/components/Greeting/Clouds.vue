<script setup>
// import gasp from "http://cdnjs.cloudflare.com/ajax/libs/gsap/3.2.4/gsap.min.js";

// watchEffect(() => {
//   this.populateClouds();
//   this.easeInClouds();
//   this.raiseClouds();
// });

function populateClouds() {
  // Populate and ease in clouds
  $("<div class='left-cloud'></div>").appendTo(".clouds");
  $("<div class='right-cloud'></div>").appendTo(".clouds");
  $("<div class='sun-cloud'></div>").appendTo(".clouds");
  $("<div class='left-cloud'></div>").appendTo("#say-hi");
  $("<div class='right-cloud'></div>").appendTo("#say-hi");
  $("<div class='sun-cloud'></div>").appendTo("#say-hi");
}

function easeInClouds() {
  gsap.from([".left-cloud", ".right-cloud", ".sun-cloud"], {
    opacity: 0,
    ease: "power3.in",
    duration: 1,
  });
}

function raiseClouds() {
  var lCloud = $(".left-cloud");
  var sunClouds = $(".sun-cloud");
  gsap.from([".left-cloud", ".right-cloud"], {
    y: lCloud.height() * 1.5,
    ease: "power2.out",
    duration: 2,
  });
  gsap.from(sunClouds, {
    y: sunClouds.height() * 1.5,
    ease: "power2.out",
    duration: 2,
  });
}
</script>

<template>
  <div class="clouds" />
</template>

<style lang="scss">
.left-cloud {
  content: url("assets/images/scenes/cloud.png");
  position: absolute;
  left: 5%;
  top: 30%;
  z-index: 1;
}

.right-cloud {
  content: url("assets/images/scenes/cloud.png");
  position: absolute;
  left: 25%;
  top: 52%;
  z-index: 1;
}

.sun-cloud {
  content: url("assets/images/scenes/sun-cloud.png");
  position: absolute;
  left: 65%;
  top: 17%;
  z-index: 1;
}
</style>
