<script setup>
import { projectData } from "components/Work/projectData.js";
import Typography from "components/Typography/Typography.vue";
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
        <Typography class="project-title bamboo-font" variant="h2">
          {{ p.title }}
        </Typography>
        <Typography class="project-subtitle" variant="h4">
          {{ p.subtitle }}
        </Typography>
        <Typography class="project-description" variant="h5">
          {{ p.description }}
        </Typography>
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
}

.project-subtitle {
  margin: 0;
  padding-bottom: 1.25rem;
  letter-spacing: 0.0625rem;
}

.project-description {
  padding-bottom: 1rem;
}

.project-link-wrapper {
  display: flex;
}

.project-btn {
  font-weight: bold;
  margin-right: 0.5rem;
}

.earlybird {
  background-color: var(--earlybird-background);

  .project-title {
    color: var(--earlybird-title);
  }
  .project-subtitle {
    color: var(--earlybird-subtitle);
  }
  .project-description {
    color: var(--earlybird-text);
  }
  .project-btn {
    background-color: var(--earlybird-btn);
    color: var(--earlybird-btn-text);
  }
}

.lacuna {
  background-color: var(--lacuna-background);

  .project-title {
    color: var(--lacuna-title);
  }
  .project-subtitle {
    color: var(--lacuna-subtitle);
  }
  .project-description {
    color: var(--lacuna-text);
  }
  .project-btn {
    background-color: var(--lacuna-btn);
    color: var(--lacuna-btn-text);
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
