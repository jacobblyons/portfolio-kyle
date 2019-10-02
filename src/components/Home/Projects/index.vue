<template>
  <div class="projects">
    <!-- background -->

    <!-- prev highlighted -->
    <div class="projects-previous-highlighted">
      <div class="projects-previous-highlighted-img-container">
        <img src="@/assets/Red Twig Kyle-mockup Dribbble big-01.png" />
      </div>
    </div>
    <!-- highlighted -->
    <div class="projects-highlighted">
      <img src="@/assets/Inspose with grey-01-01.jpg" />
    </div>
    <!-- next highlighted -->
    <div class="projects-next-highlighted">
      <div class="projects-next-highlighted-img-container">
        <img src="@/assets/Seattle Ridge Dribbble.jpg" />
      </div>
    </div>
  </div>
</template>

<script>
import BackgroundSlider from "@/components/Home/Projects/BackgroundSlider";
import VerticalLabel from "@/components/Misc/VerticalLabel.vue";

export default {
  components: {
    VerticalLabel,
    BackgroundSlider
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

// layers
$highlighted-layer: 1;
$next-highlighted-layer: 1;
$previous-highlighted-layer: 1;
$background-layer: 0;

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
    height: 100%;
    width: auto;
    overflow: hidden;
    display: flex;
    flex-flow: column nowrap;
    align-items: flex-start;
    justify-content: center;
    img {
      height: 100%;
      width: auto;
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
}
</style>
