<template>
  <div ref="grid" class="projects">
    <!-- background -->
    <!-- dead image -->
    <div id="image-1" :class="getRotationOuterDivClass(1)">
      <div :class="getRotationImgContainerClass(1)">
        <img src="@/assets/Red Twig Kyle-mockup Dribbble big-01.png" />
      </div>
    </div>
    <!-- prev highlighted -->
    <div id="image-2" :class="getRotationOuterDivClass(2)">
      <div :class="getRotationImgContainerClass(2)">
        <img src="@/assets/Red Twig Kyle-mockup Dribbble big-01.png" />
      </div>
    </div>
    <!-- highlighted -->
    <div id="image-3" :class="getRotationOuterDivClass(3)">
      <div :class="getRotationImgContainerClass(3)">
        <img :src="getPictureURL(1)" />
      </div>
    </div>
    <!-- next highlighted -->
    <div id="image-4" :class="getRotationOuterDivClass(4)">
      <div :class="getRotationImgContainerClass(4)">
        <img src="@/assets/Seattle Ridge Dribbble.jpg" />
      </div>
    </div>
    <!-- upcoming image -->
    <div id="image-5" :class="getRotationOuterDivClass(5)">
      <div :class="getRotationImgContainerClass(5)">
        <img src="@/assets/Seattle Ridge Dribbble.jpg" />
      </div>
    </div>
    <button class="projects-rotate-button" @click="rotateProductsLeft()">Rotate</button>
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
      highlightedIndex: 0,
      projectQueue: [1, 2, 3, 4, 5],
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
              nisi ut aliquip ex ea commodo consequat. `
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
  computed: {},
  methods: {
    getPictureURL(index) {
      return this.$data.projects[index].imgURL;
    },
    rotateProductsLeft() {
      let tmp = this.$data.projectQueue[0];
      this.$data.projectQueue.splice(0, 1);
      this.$data.projectQueue.push(tmp);
    },
    getRotationOuterDivClass(index) {
      let positionIndex = this.$data.projectQueue.findIndex(i => i === index);
      switch (positionIndex) {
        case 0:
          return "projects-unhighlighted";
        case 1:
          return "projects-previous-highlighted";
        case 2:
          return "projects-highlighted";
        case 3:
          return "projects-next-highlighted";
        case 4:
          return "projects-upcoming-next-highlighted";
        default:
          return "what";
      }
    },
    getRotationImgContainerClass(index) {
      let positionIndex = this.$data.projectQueue.findIndex(i => i === index);
      switch (positionIndex) {
        case 0:
          return "projects-unhighlighted-img-container";
        case 1:
          return "projects-previous-highlighted-img-container";
        case 2:
          return "projects-highlighted-img-container";
        case 3:
          return "projects-next-highlighted-img-container";
        case 4:
          return "projects-upcoming-next-highlighted-img-container";
        default:
          return "what";
      }
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
$upcoming-next-highlighted-grid-area: (
  rowstart: 2,
  rowend: 4,
  colstart: 7,
  colend: 8
);
$next-highlighted-grid-area: (
  rowstart: 2,
  rowend: 4,
  colstart: 6,
  colend: 8
);
$previous-highlighted-grid-area: (
  rowstart: 2,
  rowend: 4,
  colstart: 1,
  colend: 3
);
$unhighlighted-grid-area: (
  rowstart: 2,
  rowend: 4,
  colstart: 1,
  colend: 1
);

$rotate-button-grid-area: (
  rowstart: 4,
  rowend: 5,
  colstart: 4,
  colend: 5
);

// layers
$highlighted-layer: 1;
$upcoming-next-highlighted-layer: 1;
$next-highlighted-layer: 1;
$previous-highlighted-layer: 1;
$unhighlighted-layer: 1;
$background-layer: 0;
$rotate-button-layer: 10;

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

  &-rotate-button {
    @include gridarea($rotate-button-grid-area);
    z-index: $rotate-button-layer;
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

  @mixin faded-img {
    &-img-container {
      height: 75%;
      background-color: black;
      img {
        height: 100%;
        width: auto;
        opacity: 0.3;
      }
    }
  }

  &-upcoming-next-highlighted {
    z-index: $upcoming-next-highlighted-layer;
    @include gridarea($upcoming-next-highlighted-grid-area);
    overflow: hidden;
    width: 300%;
    margin-left: 100%;
    &-img-container {
      height: 75%;
      background-color: black;

      img {
        height: 100%;
        width: auto;
        opacity: 0.3;
      }
    }
  }

  &-next-highlighted {
    z-index: $next-highlighted-layer;
    @include gridarea($next-highlighted-grid-area);
    overflow: hidden;
    display: flex;
    flex-flow: column nowrap;
    align-items: flex-start;
    justify-content: flex-end;
    @include faded-img();
  }

  &-previous-highlighted {
    z-index: $previous-highlighted-layer;
    @include gridarea($previous-highlighted-grid-area);
    overflow: hidden;
    display: flex;
    flex-flow: column nowrap;
    align-items: flex-end;
    justify-content: flex-end;
    @include faded-img();
  }

  &-unhighlighted {
    z-index: $unhighlighted-layer;
    @include gridarea($unhighlighted-grid-area);
    overflow: hidden;
    width: auto;
    margin-right: 100%;
    &-img-container {
      height: 75%;
      background-color: black;

      img {
        height: 100%;
        width: auto;
        opacity: 0.3;
      }
    }
  }
}
</style>
