<script setup>
import { RouterLink } from "vue-router";
import Typography from "components/Typography/Typography.vue";

import WiggleButton from "components/Buttons/WiggleButton.vue";
import Social from "components/Profile/Social.vue";
</script>

<template>
  <section class="profile-container container">
    <div class="photo-resume">
      <img class="photo" src="public/images/profile-photo.png" alt="profile picture" />
      <div class="resume-link-wrapper">
        <a
          class="resume-link"
          target="_blank"
          href="images / Akbar_Marc_resume.pdf"
          download
        >
          <WiggleButton class="resume-btn" label="RESUME" />
        </a>
      </div>
    </div>

    <div class="bio">
      <div class="bio-section">
        <Typography class="bio-title bamboo-font" variant="h4"
          >I write code and climb rocks.</Typography
        >
        <Typography class="bio-text" variant="h5"
          >I live in <del>New York</del></Typography
        >
        <Typography class="bio-text" variant="h5"
          ><del class="bio-fl">Florida</del></Typography
        >
        <Typography class="bio-text" variant="h5">
          <del class="bio-ny">New York</del>
        </Typography>
        <Typography class="bio-text bio-co" variant="h5">Colorado.</Typography>
      </div>
      <div class="bio-section">
        <Typography class="bio-text" variant="h5">
          I have a passion for functional design and data and use this space to
          showcase current / past projects. Outside of tech, these designs come
          in the form of
          <a
            class="bio-link"
            href="https://thecliffsclimbing.com/blog/2016/6/24/meet-the-new-setters-marc-and-bo"
            target="_blank"
            >routesetting</a
          >.
        </Typography>
      </div>
      <div class="bio-section">
        <Typography class="bio-text" variant="h5">
          Check out my
          <RouterLink class="bio-link" to="/#work">work</RouterLink> or find me
          through the social links below.
        </Typography>
      </div>
      <Social />
    </div>
  </section>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.profile-container {
  padding-top: 4rem;
  padding-bottom: 4rem;
  display: flex;
  align-items: flex-start;
  justify-content: space-around;
}

.photo-resume {
  width: 100%;
  text-align: center;
}

.photo {
  width: 65%;
  min-width: 313px;
  padding-bottom: 2rem;
}

.resume-link-wrapper {
  width: fit-content;
  margin: auto;
}

.resume-btn {
  background-color: $custom-teal;
  color: var(--wb-btn-text);
}

.bio {
  width: 75%;
}

.bio-section {
  padding-bottom: 2rem;
}

.bio-title {
  margin: 0;
  text-transform: uppercase;
  padding-bottom: 2rem;
  color: var(--about-title);
}

.bio-text {
  margin: 0;
  color: var(--about-text);
}

.bio-link {
  color: $custom-teal;
}

.bio-fl {
  padding-left: 7rem;
}

.bio-ny {
  padding-left: 10rem;
}

.bio-co {
  padding-left: 13rem;
}
</style>
