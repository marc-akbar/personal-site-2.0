<script setup>
const props = defineProps({
  label: String,
});
</script>

<template>
  <button class="btn">
    <span class="label">{{ label }}</span>
  </button>
</template>

<style lang="scss" scoped>
.btn {
  position: relative;
  height: 36px;
  outline: none;
  text-decoration: none;
  border: none;
  border-radius: 4px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  text-transform: uppercase;
  opacity: 1;

  &:hover {
    animation: rotate 0.7s ease-in-out both;

    .label {
      animation: storm 0.7s ease-in-out both;
      animation-delay: 0.06s;
    }
  }
}

.label {
  font-size: 14px;
  font-weight: bold;
  letter-spacing: 0.5px;
}

@keyframes rotate {
  0% {
    transform: rotate(0deg) translate3d(0, 0, 0);
  }
  25% {
    transform: rotate(3deg) translate3d(0, 0, 0);
  }
  50% {
    transform: rotate(-3deg) translate3d(0, 0, 0);
  }
  75% {
    transform: rotate(1deg) translate3d(0, 0, 0);
  }
  100% {
    transform: rotate(0deg) translate3d(0, 0, 0);
  }
}

@keyframes storm {
  0% {
    transform: translate3d(0, 0, 0) translateZ(0);
  }
  25% {
    transform: translate3d(4px, 0, 0) translateZ(0);
  }
  50% {
    transform: translate3d(-3px, 0, 0) translateZ(0);
  }
  75% {
    transform: translate3d(2px, 0, 0) translateZ(0);
  }
  100% {
    transform: translate3d(0, 0, 0) translateZ(0);
  }
}
</style>
