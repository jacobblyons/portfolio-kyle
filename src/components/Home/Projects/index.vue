<template>
  <div ref="grid" class="projects">
    <div class="projects-highlighted">
      <div class="projects-highlighted-img-container">
        <img :src="project.imgURL" />
      </div>
    </div>
    <!-- prev button -->
    <button class="projects-rotate-left-button" @click="rotateProductsLeft()">&lt;</button>
    <!-- next button -->
    <button class="projects-rotate-right-button" @click="rotateProductsRight()">&gt;</button>
    <!-- vertical label -->
    <div class="projects-vertical-label">
      <vertical-label title="Selected Works"></vertical-label>
    </div>
    <!-- project title -->
    <div class="projects-title">
      <p class="projects-title-index">{{`-0${projectIndex+1}`}}</p>
      <p class="projects-title-name">{{project.title}}</p>
      <button>VIEW PROJECT</button>
    </div>
    <!-- project description -->
    <div class="projects-description">
      <p class="projects-description-header">{{project.jobDescription.title}}</p>
      <p class="projects-description-content">{{project.jobDescription.content}}</p>
    </div>
  </div>
</template>

<script>
import VerticalLabel from "@/components/Misc/VerticalLabel.vue";
import InsposeImage from "@/assets/Inspose with grey-01-01.jpg";
import SeattleRidgeImage from "@/assets/Seattle Ridge Dribbble.jpg";
import RedTwigImage from "@/assets/Red Twig Kyle-mockup Dribbble big-01.png";
export default {
  components: {
    VerticalLabel
  },
  data() {
    return {
      projectIndex: 0,
      projects: [
        {
          title: "Inspose",
          jobDescription: {
            title: "Re-Branding / Package Design",
            content: `Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
              sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
              Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris 
              nisi ut aliquip ex ea commodo consequat. `
          },
          imgURL: InsposeImage
        },
        {
          title: "Seattle Ridge",
          jobDescription: {
            title: "Re-Branding / Package Design",
            content: `Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
              sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
              Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris 
              nisi ut aliquip ex ea commodo consequat.`
          },
          imgURL: SeattleRidgeImage
        },
        {
          title: "Red Twig",
          jobDescription: {
            title: "Re-Branding / Package Design",
            content: `Lorem ipsum dolor sit amet, consectetur adipiscing elit, 
              sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. 
              Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris 
              nisi ut aliquip ex ea commodo consequat. `
          },
          imgURL: RedTwigImage
        }
      ]
    };
  },
  computed: {
    project() {
      return this.$data.projects[this.$data.projectIndex];
    }
  },
  methods: {
    getPictureURL(index) {
      return this.$data.projects[index].imgURL;
    },
    rotateProductsRight() {
      this.$data.projectIndex =
        (this.$data.projectIndex + 1) % this.$data.projects.length;
    },
    rotateProductsLeft() {
      this.$data.projectIndex =
        this.$data.projectIndex - 1 < 0
          ? this.$data.projects.length - 1
          : this.$data.projectIndex - 1;
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../../../styles/mixins";
// cols
$margin-width: 5em;
$brand-width: 5em;
$image-gutters-width: 5em;
$highlighted-width: min-content;
$title-overlap-width: 10em;
$textbox-width: 1fr;
// rows
$navbar-height: 5em;
$top-margin-height: 5em;
$main-body-height: 1fr;
$left-button-height: 5em;
$footer-height: 5em;
// areas
$background-grid-area: (
  rowstart: 1,
  rowend: 4,
  colstart: 1,
  colend: 8
);

$highlighted-grid-area: (
  rowstart: 2,
  rowend: 5,
  colstart: 3,
  colend: 5
);

$rotate-left-button-grid-area: (
  rowstart: 4,
  rowend: 5,
  colstart: 4,
  colend: 5
);

$rotate-right-button-grid-area: (
  rowstart: 5,
  rowend: 6,
  colstart: 4,
  colend: 5
);

$vertical-label-grid-area: (
  rowstart: 3,
  rowend: 4,
  colstart: 2,
  colend: 3
);

$title-grid-area: (
  rowstart: 3,
  rowend: 4,
  colstart: 4,
  colend: 7
);

$description-grid-area: (
  rowstart: 4,
  rowend: 6,
  colstart: 5,
  colend: 9
);

// layers
$highlighted-layer: 1;
$upcoming-next-highlighted-layer: 1;
$next-highlighted-layer: 1;
$previous-highlighted-layer: 1;
$unhighlighted-layer: 1;
$background-layer: 0;
$rotate-left-button-layer: 10;
$rotate-right-button-layer: 10;
$vertical-label-layer: 10;
$title-layer: 12;
$description-layer: 12;

.projects {
  width: 100%;
  height: 100%;
  max-height: 100vh;
  display: grid;
  grid-template-columns:
    $margin-width
    $brand-width
    $highlighted-width
    $title-overlap-width
    $image-gutters-width
    $textbox-width
    $margin-width;

  grid-template-rows:
    $navbar-height
    $top-margin-height
    $main-body-height
    $left-button-height
    $footer-height;

  &-rotate-left-button {
    @include gridarea($rotate-left-button-grid-area);
    z-index: $rotate-left-button-layer;
  }

  &-rotate-right-button {
    @include gridarea($rotate-right-button-grid-area);
    z-index: $rotate-right-button-layer;
  }

  &-vertical-label {
    @include gridarea($vertical-label-grid-area);
    z-index: $vertical-label-layer;
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    justify-content: center;
  }

  &-title {
    @include gridarea($title-grid-area);
    z-index: $title-layer;
    display: flex;
    flex-flow: column;
    align-self: center;
    justify-content: flex-start;
    &-index {
      margin: 0;
      color: white;
      text-shadow: 2px 2px 12px #000000;
      letter-spacing: 0.2em;
      font: {
        size: 3em;
        family: "komu-b";
      }
    }
    &-name {
      margin: 0;
      color: white;
      text-shadow: 2px 2px 10px #000000;
      font: {
        size: 6em;
        family: "futura-pt";
      }
    }
  }

  &-description {
    @include gridarea($description-grid-area);
    z-index: $description-layer;
    background-color: black;
    width: 100%;
    display: flex;
    flex-flow: column nowrap;
    align-items: flex-start;
    justify-content: center;
    padding: 1em;
    &-header {
      margin: 0;
      letter-spacing: 0.1em;
      color: white;
      font: {
        size: 2em;
        family: "komu-b";
      }
    }

    &-content {
      margin: 0;
      letter-spacing: 0.1em;
      color: white;
      font: {
        size: 1em;
        family: "futura-pt";
      }
    }
  }

  &-background {
    z-index: $background-layer;
    @include gridarea($background-grid-area);
    height: 100%;
    object-fit: cover;
  }

  &-highlighted {
    z-index: $highlighted-layer;
    @include gridarea($highlighted-grid-area);
    margin-left: $image-gutters-width;
    overflow: hidden;
    height: 100%;
    width: auto;
    &-img-container {
      overflow: hidden;
      height: 100%;
      width: auto;
      display: flex;
      flex-flow: column nowrap;
      align-items: flex-start;
      justify-content: center;
      img {
        height: 100%;
        width: auto;
      }
    }
  }
}
</style>