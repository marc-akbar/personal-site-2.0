<script setup>
import WiggleButton from "components/Buttons/WiggleButton.vue";
import Typography from "components/Typography/Typography.vue";

const props = defineProps({
  darkMode: Boolean,
});
</script>

<template>
  <section class="footer-container">
    <Typography class="footer-title cursive-font" variant="h1"
      >Say hi.</Typography
    >
    <Typography class="footer-text" variant="h4">
      I don't bite and would love to chat. Feel free to reach out.
    </Typography>

    <div class="footer-link-wrapper">
      <a href="mailto:marc.akbar@gmail.com" class="footer-link">
        <WiggleButton class="footer-btn" label="MESSAGE ME" icon="mail" />
      </a>
    </div>

    <div v-if="!props.darkMode" class="left-cloud" ref="leftCloud" />
    <div v-if="!props.darkMode" class="right-cloud" ref="rightCloud" />
    <div v-if="!props.darkMode" class="sun-cloud" ref="sunCloud" />
  </section>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.footer-container {
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
  z-index: 1;
  padding-bottom: 1rem;
  color: var(--footer-title);
}

.footer-text {
  padding-bottom: 1rem;
  color: var(--footer-text);
  z-index: 1;
}

.footer-link-wrapper {
  width: fit-content;
  margin: auto;
  z-index: 1;
}

.footer-btn {
  background-color: $btn-color;
  font-weight: bold;
  letter-spacing: 0.0625rem;
  padding: 1.25rem 2.25rem;
  z-index: 1;
  font-size: 1rem;
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
