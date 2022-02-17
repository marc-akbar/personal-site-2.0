<script setup>
import Greeting from "components/Greeting/Greeting.vue";
import Work from "components/Work/Work.vue";
import Contact from "components/Footer/Contact.vue";

const props = defineProps({
  darkMode: Boolean,
});
</script>

<template>
  <Greeting :darkMode="darkMode" />
  <Work />
  <Contact :darkMode="darkMode" />
</template>
