<script setup>
const props = defineProps({
  changeTheme: Function,
});
</script>

<template>
  <div class="sidenav-root">
    <div class="btn default" @click="props.changeTheme('default')" />
    <div class="btn nes" @click="props.changeTheme('nes')" />
  </div>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.sidenav-root {
  z-index: 500;
  height: 100%;
  position: fixed;
  display: flex;
  flex-direction: column;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.3);
}

.btn {
  width: 3rem;
  height: 100%;
}

.default {
  background-color: $day-scene-background;
}

.nes {
  background-color: #209cee;
}
</style>
