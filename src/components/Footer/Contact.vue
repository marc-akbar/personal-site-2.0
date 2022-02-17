<script setup>
import WiggleButton from "components/Buttons/WiggleButton.vue";

const props = defineProps({
  darkMode: Boolean,
});
</script>

<template>
  <section class="container">
    <h4 class="footer-title">Say hi.</h4>
    <p class="footer-text">
      I don't bite and would love to chat. Feel free to reach out.
    </p>

    <a href="mailto:marc.akbar@gmail.com" class="footer-link">
      <WiggleButton class="footer-btn" label="MESSAGE ME" icon="mail" />
    </a>

    <div v-if="!darkMode" class="left-cloud" ref="leftCloud" />
    <div v-if="!darkMode" class="right-cloud" ref="rightCloud" />
    <div v-if="!darkMode" class="sun-cloud" ref="sunCloud" />
  </section>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.container {
  position: relative;
  margin: 0;
  padding-top: 7rem;
  padding-bottom: 7rem;
  text-align: center;
  background-color: var(--footer-background);
  z-index: 0;
}

.footer-title {
  margin: 0;
  font-size: 5rem;
  font-family: "Satisfy", cursive, sans-serif;
  font-weight: 200;
  color: var(--footer-title);
  z-index: 1;
}

.footer-text {
  font-size: 1.75rem;
  padding-bottom: 1rem;
  color: var(--footer-text);
  z-index: 1;
}

.footer-link {
  text-decoration: none;
  display: inline-block;
  z-index: 1;
}

.footer-btn {
  background-color: $btn-color;
  font-weight: bold;
  letter-spacing: 0.0625rem;
  padding: 1.75rem 2.25rem;
  z-index: 1;

  .btn span {
    font-size: 1rem;
  }
}

.left-cloud {
  content: url("images/scenes/cloud.png");
  position: absolute;
  left: 10%;
  top: 42%;
  z-index: -1;
}

.right-cloud {
  content: url("images/scenes/cloud.png");
  position: absolute;
  left: 70%;
  top: 12%;
  z-index: -1;
}

.sun-cloud {
  content: url("images/scenes/sun-cloud.png");
  position: absolute;
  left: 57%;
  top: 57%;
  z-index: -1;
}
</style>
