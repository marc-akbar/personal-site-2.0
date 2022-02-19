<script setup>
import { RouterLink } from "vue-router";
import WiggleButton from "components/Buttons/WiggleButton.vue";
import Social from "components/Profile/Social.vue";
</script>

<template>
  <section class="profile-container container">
    <div class="photo-resume">
      <img class="photo" src="images/profile-photo.png" alt="profile picture" />
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
        <h5 class="bio-title">I write code and climb rocks.</h5>
        <p class="bio-text">I live in <del>New York</del></p>
        <p class="bio-text"><del class="bio-fl">Florida</del></p>
        <p class="bio-text">
          <del class="bio-ny">New York</del>
        </p>
        <p class="bio-text bio-co">Colorado.</p>
      </div>
      <div class="bio-section">
        <p class="bio-text">
          I have a passion for functional design and data and use this space to
          showcase current / past projects. Outside of tech, these designs come
          in the form of
          <a
            class="bio-link"
            href="https://thecliffsclimbing.com/blog/2016/6/24/meet-the-new-setters-marc-and-bo"
            target="_blank"
            >routesetting</a
          >.
        </p>
      </div>
      <div class="bio-section">
        <p class="bio-text">
          Check out my
          <RouterLink class="bio-link" to="/#work">work</RouterLink> or find me
          through the social links below.
        </p>
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
  width: 50%;
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
  font-family: "Baloo Tammudu 2", cursive, sans-serif;
  font-size: 1.75rem;
  text-transform: uppercase;
  padding-bottom: 2rem;
  color: var(--about-title);
}

.bio-text {
  margin: 0;
  font-size: 1.25rem;
  font-weight: normal;
  color: var(--about-text);
}

.bio-link {
  color: $custom-teal;
}

.bio-fl {
  padding-left: 100px;
}

.bio-ny {
  padding-left: 140px;
}

.bio-co {
  padding-left: 190px;
}
</style>
