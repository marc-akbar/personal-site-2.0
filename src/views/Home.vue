<script setup>
import Greeting from "components/Greeting/Greeting.vue";
import Work from "components/Work/Work.vue";
</script>

<template>
  <Greeting :darkMode="darkMode" />
  <Work :darkMode="darkMode" />
</template>
