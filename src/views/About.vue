<script setup>
import Greeting from "components/Greeting/Greeting.vue";
import Profile from "components/Profile/Profile.vue";
import Contact from "components/Footer/Contact.vue";

const props = defineProps({
  darkMode: Boolean,
});
</script>

<template>
  <Greeting :darkMode="props.darkMode" title="about" />
  <Profile />
  <Contact :darkMode="props.darkMode" />
</template>
