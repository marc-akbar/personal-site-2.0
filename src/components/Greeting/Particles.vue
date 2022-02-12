<template>
  <div class="particle particle-1"></div>
  <div class="particle particle-2"></div>
</template>

<style land="scss">
@keyframes particleAnimation {
  from {
    left: -2000px;
  }
  to {
    left: calc(100% + 500px);
  }
}

.particle {
  position: absolute;
  left: 0px;
  top: 10vw;
  width: 1px;
  height: 1px;
  background-color: white;
  animation-name: particleAnimation;
  animation-timing-function: linear;
  animation-iteration-count: infinite;
}

.particle::before {
  content: "";
  position: absolute;
  display: block;
  width: 150px;
  right: 1px;
  top: 0px;
  height: 1px;
  background: linear-gradient(
    to right,
    rgba(0, 0, 0, 0) 0%,
    rgba(255, 255, 255, 0.4) 100%
  );
}

.particle-1 {
  animation-duration: 13s;
  top: 30%;
}

.particle-2 {
  animation-duration: 23s;
  top: 65%;
}
</style>
