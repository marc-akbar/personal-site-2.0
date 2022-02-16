<script setup>
import Greeting from "components/Greeting/Greeting.vue";
import Work from "components/Work/Work.vue";

const props = defineProps({
  darkMode: Boolean,
});
</script>

<template>
  <Greeting :darkMode="darkMode" />
  <Work :darkMode="darkMode" />
</template>
