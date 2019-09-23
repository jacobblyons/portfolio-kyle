<template>
  <div class="home">
    <!-- portrait background -->
    <div class="home-portrait-background">
      <img class="home-portrait-background-img" src="@/assets/header_background.png" />
    </div>
    <!-- portrait foreground-->
    <div class="home-portrait-foreground">
      <img class="home-portrait-foreground-img" src="@/assets/header_cutout.png" />
    </div>
    <!-- portrait banner -->
    <div class="home-portrait-banner">
      <img class="home-portrait-banner-img" src="@/assets/RHODES.png" />
    </div>
    <!-- left label -->
    <div class="home-left-label">
      <vertical-label title="Introduction"></vertical-label>
    </div>
    <!-- content -->
    <div class="home-content">
      <home-content></home-content>
    </div>
    <!-- brand -->
    <div class="home-brand">
      <img class="home-brand-icon" src="@/assets/Asset 6.png" />
    </div>
    <!-- collapse -->
    <div class="home-collapse">
      <collapse-button @ondown="openSidebar" @onreleased="closeSidebar" />
    </div>
    <!-- sidebar -->
    <div class="home-sidebar">
      <sidebar :opened="sidebarOpened" />
    </div>
  </div>
</template>

<script>
import Brand from "@/components/Navbar/Brand.vue";
import VerticalLabel from "@/components/Misc/VerticalLabel.vue";
import HomeContent from "@/components/Home/Landing/HomeContent.vue";
import CollapseButton from "@/components/Navbar/CollapseButton.vue";
import Sidebar from "@/components/Sidebar";

export default {
  name: "landing",
  components: {
    Brand,
    VerticalLabel,
    HomeContent,
    CollapseButton,
    Sidebar
  },
  data() {
    return {
      sidebarOpened: false
    };
  },
  methods: {
    openSidebar() {
      this.$data.sidebarOpened = true;
    },
    closeSidebar() {
      this.$data.sidebarOpened = false;
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../../../styles/mixins";
.home {
  width: 100%;
  height: 100%;
  max-height: 100vh;
  min-height: 780px;
  overflow: hidden;
  display: grid;
  grid-template-columns: 5em 5em auto 5em 5em;
  grid-template-rows: 10em 10em repeat(2, 1fr);
  grid-template-areas:
    ". brand . collapse ."
    ". . . . . "
    ". content content content ."
    ". . . . .";
  @include desktop {
    grid-template-columns: 5em 5em 7em auto 4em 4em 5em 4em;
    grid-template-rows: 10em 10em repeat(2, auto);
    grid-template-areas:
      ".......  brand   .......   .......   .......  .......  collapse ......."
      ".......  ....... .......   .......   .......  .......  .......  ......."
      ".......  title   .......   content   .......  .......  .......  ......."
      ".......  ....... .......   .......   .......  .......  .......  .......";
  }

  &-collapse {
    grid-area: collapse;
    z-index: 22;
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    justify-content: center;
  }

  &-sidebar {
    grid-area: 1 / 6 / 5 / 9;
    z-index: 20;
  }

  &-brand {
    grid-area: brand;
    z-index: 10;
    &-icon {
      width: 100%;
    }
  }

  @mixin portrait {
    width: 100%;
    height: 100vh;
    grid-area: 2 /1 / 5 / 6;
    @include desktop {
      grid-area: 2 /1 / 5 / 9;
      min-height: 780px;
    }
    display: flex;
    overflow: hidden;
    flex-flow: row nowrap;
    align-items: flex-start;
    justify-content: center;
    &-img {
      object-fit: cover;
      height: 100%;
    }
  }

  &-portrait-foreground {
    @include portrait;
    z-index: 12;
  }

  &-portrait-background {
    @include portrait;
    z-index: 10;
  }

  &-portrait-banner {
    z-index: 10;
    overflow-y: hidden;
    width: 100%;
    display: none;
    @include desktop {
      grid-area: 2 /4 / 5 / 9;
      display: flex;
      flex-flow: row nowrap;
      align-items: flex-start;
      justify-content: flex-start;
    }
    &-img {
      width: 900px;
    }
  }

  &-left-label {
    z-index: 10;
    grid-area: title;
    display: none;
    @include desktop {
      display: flex;
      flex-flow: column nowrap;
      align-items: center;
      justify-content: flex-start;
    }
  }

  &-content {
    z-index: 15;
    grid-area: content;
    display: flex;
    flex-flow: column nowrap;
    align-items: flex-start;
    justify-content: center;
  }
}
</style>

