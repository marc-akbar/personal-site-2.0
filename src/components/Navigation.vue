<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <nav class="z-depth-0">
    <div class="time-toggle">
      <!-- From Benjamin Réthoré https://codepen.io/bnthor -->
      <div class="toggleWrapper">
        <input type="checkbox" class="dn" id="dn" checked />
        <label for="dn" class="toggle">
          <span class="toggle__handler">
            <span class="crater crater--1"></span>
            <span class="crater crater--2"></span>
            <span class="crater crater--3"></span>
          </span>
          <span class="star star--1"></span>
          <span class="star star--2"></span>
          <span class="star star--3"></span>
          <span class="star star--4"></span>
          <span class="star star--5"></span>
          <span class="star star--6"></span>
        </label>
      </div>
    </div>

    <div class="container">
      <div class="nav-wrapper">
        <ul class="right hide-on-med-and-down">
          <RouterLink class="link" to="/">Home</RouterLink>
          <RouterLink class="link" to="/about">About</RouterLink>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style lang="scss">
@import "@/assets/base.scss";

nav {
  position: absolute;
  z-index: 1;
  background-color: var(--nav-background);

  & a {
    color: var(--sidenav-trigger);
  }

  & .time-toggle {
    position: fixed;
    top: 43px;
    left: 45px;
  }

  & .nav-wrapper {
    & .link {
      margin-top: 15px;
      margin-bottom: 15px;
      font-family: "Baloo Tammudu 2", cursive, sans-serif;
      font-weight: 600;
      font-size: 20px;
      padding-left: 40px;
      padding-right: 40px;
      color: var(--nav-btn);

      & i {
        font-size: 50px;
      }
    }

    & a:hover {
      background-color: inherit !important;
      color: $custom-teal !important;
    }
  }
}

.sidenav {
  padding-top: 20px;
  background-color: var(--sidenav-background);

  & li {
    padding-top: 15px;

    & a {
      font-family: "Baloo Tammudu 2", cursive, sans-serif;
      font-weight: 600;
      font-size: 16px;
      color: var(--sidenav-btn);
    }
  }
}
</style>
