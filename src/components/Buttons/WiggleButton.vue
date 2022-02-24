<script setup>
import Typography from "components/Typography/Typography.vue";

const props = defineProps({
  label: String,
  icon: String,
});
</script>

<template>
  <div class="btn-wrapper">
    <button class="btn">
      <Typography>
        <div class="label">
          <i v-if="icon" class="material-icons icon">{{ props.icon }}</i>
          {{ props.label }}
        </div>
      </Typography>
    </button>
  </div>
</template>

<style lang="scss" scoped>
.btn-wrapper {
  background-color: inherit;
  color: rgba(0, 0, 0, 0.87);
  border: none;
  border-radius: 4px;
  padding: 0.75rem 1rem;

  &:hover {
    animation: rotate 0.7s ease-in-out both;

    .label {
      animation: storm 0.7s ease-in-out both;
      animation-delay: 0.06s;
    }
  }
}

.btn {
  position: relative;
  border: none;
  outline: none;
  background-color: inherit;
  color: inherit;
  text-transform: uppercase;
  cursor: pointer;
  opacity: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.icon {
  padding-right: 0.75rem;
}

.label {
  font-weight: bold;
  letter-spacing: 0.5px;
  display: flex;
  align-items: center;
  justify-content: space-around;
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
