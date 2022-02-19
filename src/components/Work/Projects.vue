<script setup>
import { projectData } from "components/Work/projectData.js";
import WiggleButton from "components/Buttons/WiggleButton.vue";
</script>

<template>
  <div :class="p.class" v-for="(p, index) in projectData">
    <div class="project-container container">
      <img
        class="project-image"
        :style="[index & 1 ? { order: 3 } : { order: 1 }]"
        :src="p.image.source"
        :alt="p.image.description"
      />

      <div class="project-gap" />

      <div :style="[index & 1 ? { order: 1 } : { order: 3 }]">
        <h4 class="project-title">{{ p.title }}</h4>
        <h6 class="project-subtitle">{{ p.subtitle }}</h6>
        <p class="project-description">{{ p.description }}</p>
        <div class="project-link-wrapper">
          <a v-for="l in p.links" target="_blank" :href="l.url">
            <WiggleButton class="project-btn" :label="l.label" />
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import "assets/palette.scss";

.project-container {
  padding: 7rem;
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.project-gap {
  padding-left: 5rem;
  order: 2;
}

.project-image {
  max-width: 60%;
  min-width: 313px;
}

.project-title {
  margin: 0;
  font-family: "Baloo Tammudu 2", cursive, sans-serif;
  font-size: 2.2rem;
  font-weight: 200;
}

.project-subtitle {
  margin: 0;
  font-size: 1.1rem;
  font-weight: normal;
  padding-bottom: 1.25rem;
  letter-spacing: 0.0625rem;
}

.project-description {
  font-size: 1rem;
  font-weight: normal;
}

.project-link-wrapper {
  display: flex;
}

.project-btn {
  font-weight: bold;
  margin-right: 0.5rem;
}

.earlybird {
  background-color: var(--eb-background);

  .project-title {
    color: var(--eb-title);
  }
  .subtitle {
    color: var(--eb-subtitle);
  }
  .description {
    color: var(--eb-text);
  }
  .btn {
    background-color: var(--eb-btn);
    color: var(--eb-btn-text);
  }
}

.trail-buddy {
  background-color: var(--tb-background);

  .project-title {
    color: var(--tb-title);
  }
  .project-subtitle {
    color: var(--tb-subtitle);
  }
  .project-description {
    color: var(--tb-text);
  }
  .project-btn {
    background-color: var(--tb-btn);
    color: var(--tb-btn-text);
  }
}

.finance {
  background-color: var(--ft-background);

  .project-title {
    color: var(--ft-title);
  }
  .project-subtitle {
    color: var(--ft-subtitle);
  }
  .project-description {
    color: var(--ft-text);
  }
  .project-btn {
    background-color: var(--ft-btn);
    color: var(--ft-btn-text);
  }
}

.weather {
  background-color: var(--wb-background);

  .project-title {
    color: var(--wb-title);
  }
  .project-subtitle {
    color: var(--wb-subtitle);
  }
  .project-description {
    color: var(--wb-text);
  }
  .project-btn {
    background-color: var(--wb-btn);
    color: var(--wb-btn-text);
  }
}

.personal {
  background-color: var(--personal-background);

  .project-title {
    color: var(--personal-title);
  }
  .project-subtitle {
    color: var(--personal-subtitle);
  }
  .project-description {
    color: var(--personal-text);
  }
  .project-btn {
    background-color: var(--personal-btn);
    color: var(--personal-btn-text);
  }
}
</style>
