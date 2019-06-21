<template>
  <div class="home">
    <navbar class="home-nav"></navbar>
    <div class="home-portrait-background">
      <img class="home-portrait-background-img" src="../assets/header_background - cropped.png">
    </div>
    <div class="home-portrait-foreground">
      <img class="home-portrait-foreground-img" src="../assets/header_cutout.png">
    </div>
    <div class="home-portrait-banner">
      <img class="home-portrait-banner-img" src="../assets/Rhodes .png">
    </div>
    <div class="home-left-label">
      <vertical-label title="Introduction"></vertical-label>
    </div>
    <div class="home-content">
      <home-content></home-content>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";
import VerticalLabel from "@/components/VerticalLabel.vue";
import HomeContent from "@/components/HomeContent.vue";

export default {
  name: "home",
  components: {
    Navbar,
    VerticalLabel,
    HomeContent
  }
};
</script>

<style lang="scss" scoped>
.home {
  width: 100%;
  height: 100%;
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  grid-template-rows: 12rem repeat(2, 1fr) 5rem;
  grid-template-areas:
    "navbar navbar navbar  navbar  navbar  navbar"
    "title banner banner banner banner contact"
    "title content content content content contact"
    ". . . . . . ";
  &-nav {
    grid-area: navbar;
    z-index: 10;
  }

  &-portrait-foreground {
    z-index: 12;
    grid-area: 2 / 1/ 7/ 7;
    width: 100%;
    display: flex;
    overflow: hidden;
    flex-flow: row nowrap;
    align-items: flex-start;
    justify-content: center;
    &-img {
      width: 100%;
      min-width: 1000px;
      height: auto;
    }
  }

  &-portrait-background {
    z-index: 10;
    overflow-y: hidden;
    grid-area: 2 / 1/ 7/ 7;
    width: 100%;
    display: flex;
    flex-flow: row nowrap;
    align-items: flex-start;
    justify-content: center;
    &-img {
      width: 100%;
      min-width: 1000px;
      height: auto;
    }
  }

  &-portrait-banner {
    z-index: 10;
    overflow-y: hidden;
    grid-area: 2 / 2/ 7/ 6;
    width: 100%;
    display: flex;
    flex-flow: row nowrap;
    align-items: flex-start;
    justify-content: center;
    &-img {
      width: 100%;
      min-width: 500px;
      height: auto;
    }
  }

  &-left-label {
    z-index: 10;
    grid-area: title;
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
    justify-content: center;
  }

  &-content {
    z-index: 15;
    grid-area: content;
  }
}
</style>

