<script setup>
import { ref } from "vue";
import Navigation from "components/Navigation/Navigation.vue";

let darkMode = ref(false);

const storedDarkMode = localStorage.getItem("darkMode");
if (!storedDarkMode) {
  localStorage.setItem("darkMode", "FALSE");
}

if (storedDarkMode === "FALSE") darkMode = ref(false);
if (storedDarkMode === "TRUE") darkMode = ref(true);

function toggleTime() {
  const newValue = !darkMode.value;
  darkMode.value = newValue;
  localStorage.setItem("darkMode", newValue ? "TRUE" : "FALSE");
}
</script>

<template>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <meta name="author" content="Marc Akbar" />
    <meta
      name="description"
      content="I'm Marc. I write code and climb rocks."
    />
    <meta
      name="keywords"
      content="marc, akbar, marc akbar, developer, web development, software engineer, design"
    />

    <meta property="og:title" content="Marc Akbar" />
    <meta property="og:description" content="Portfolio site for Marc Akbar." />
    <meta property="og:type" content="website" />
    <meta
      property="og:image"
      content="www.marcakbar.dev/images/card-image.png"
    />
    <meta property="og:image:width" content="1200" />
    <meta property="og:image:height" content="630" />
    <meta property="og:url" content="https://www.marcakbar.dev/" />
    <meta property="og:site_name" content="Marc Akbar Portfolio" />

    <meta name="twitter:card" content="summary_large_image" />
    <meta name="twitter:creator" content="@snack_bar13" />
    <meta
      name="twitter:image"
      content="https://www.marcakbar.dev/images/card-image.png"
    />
    <meta name="twitter:image:alt" content="Home page in day and night" />

    <!-- Import Google Icon Font -->
    <link
      href="//fonts.googleapis.com/icon?family=Material+Icons"
      rel="stylesheet"
    />
    <!-- Google Fonts -->
    <link
      href="//fonts.googleapis.com/css2?family=Baloo+Tammudu+2:wght@600&family=Satisfy&display=swap"
      rel="stylesheet"
    />
    <title>Marc Akbar</title>
  </head>

  <div class="wrapper" :class="darkMode ? 'night' : 'day'">
    <Navigation :darkMode="darkMode" :toggleTime="toggleTime" />
    <RouterView :darkMode="darkMode" />
  </div>
</template>

<style lang="scss">
@import "assets/palette.scss";

body {
  margin: 0 !important;
}

p {
  letter-spacing: 0.02857rem;
}

.wrapper {
  min-height: 100vh;
  position: relative;
  overflow-x: hidden;
  overflow-y: hidden;
  background-color: var(--background);
  transition: color 0.5s ease, background-color 0.5s ease;
}
</style>
