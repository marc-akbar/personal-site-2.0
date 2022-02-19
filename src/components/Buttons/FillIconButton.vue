<script setup>
const props = defineProps({
  href: String,
});
</script>

<template>
  <div class="item">
    <a class="item-link" :href="props.href" target="_blank"><slot /></a>
  </div>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.item {
  height: 100%;
  max-height: 52px;
  transition: all 0.25s ease-out;
  filter: var(--logo-filter);
  -webkit-filter: var(--logo-filter);
}
.item:hover {
  cursor: pointer;
  filter: var(--logo-hover-filter);
  -webkit-filter: var(--logo-hover-filter);
}
</style>
