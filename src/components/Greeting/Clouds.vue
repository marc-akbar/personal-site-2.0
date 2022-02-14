<script setup>
import { ref, onMounted } from "vue";
import { gsap } from "gsap";

const leftCloud = ref(null);
const sunCloud = ref(null);

function easeInClouds() {
  gsap.from([".left-cloud", ".right-cloud", ".sun-cloud"], {
    opacity: 0,
    ease: "power3.in",
    duration: 1,
  });
}

function raiseClouds() {
  gsap.from([".left-cloud", ".right-cloud"], {
    y: leftCloud.value.clientHeight * 1.5,
    ease: "power2.out",
    duration: 2,
  });
  gsap.from(".sun-cloud", {
    y: sunCloud.value.clientHeight * 1.5,
    ease: "power2.out",
    duration: 2,
  });
}

onMounted(() => {
  easeInClouds();
  raiseClouds();
});
</script>

<template>
  <div>
    <div class="left-cloud" ref="leftCloud" />
    <div class="right-cloud" ref="rightCloud" />
    <div class="sun-cloud" ref="sunCloud" />
  </div>
</template>

<style lang="scss">
.left-cloud {
  content: url("images/scenes/cloud.png");
  position: absolute;
  left: 5%;
  top: 30%;
  z-index: 1;
}

.right-cloud {
  content: url("images/scenes/cloud.png");
  position: absolute;
  left: 25%;
  top: 52%;
  z-index: 1;
}

.sun-cloud {
  content: url("images/scenes/sun-cloud.png");
  position: absolute;
  left: 65%;
  top: 17%;
  z-index: 1;
}
</style>
