<template>
  <div id="app">
    <!-- content -->
    <div id="app-content">
      <router-view />
    </div>
    <!-- brand -->
    <div id="app-brand">
      <img src="@/assets/Asset 6.png" />
    </div>
    <!-- collapse -->
    <div id="app-collapse">
      <collapse-button @ondown="openSidebar" @onreleased="closeSidebar" />
    </div>
    <!-- sidebar -->
    <div id="app-sidebar">
      <sidebar :opened="sidebarOpened" />
    </div>
  </div>
</template>

<script>
import Brand from "@/components/Navbar/Brand.vue";
import VerticalLabel from "@/components/Misc/VerticalLabel.vue";
import CollapseButton from "@/components/Navbar/CollapseButton.vue";
import Sidebar from "@/components/Sidebar";

export default {
  components: {
    Brand,
    VerticalLabel,
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

<style lang="scss">
@import "/styles/mixins";
$brand-layer: 10;
$collapse-layer: 11;
$sidebar-layer: 10;
$collapse-grid-area: (
  rowstart: 1,
  rowend: 2,
  colstart: 7,
  colend: 7
);
$brand-grid-area: (
  rowstart: 1,
  rowend: 2,
  colstart: 2,
  colend: 3
);
$sidebar-grid-area: (
  rowstart: 1,
  rowend: 4,
  colstart: 6,
  colend: 9
);
$content-grid-area: (
  rowstart: 1,
  rowend: 4,
  colstart: 1,
  colend: 9
);

body {
  margin: 0;
  height: 100vh;
}
#app {
  height: 100vh;
  display: grid;
  grid-template-rows: min-content repeat(2, 1fr);
  grid-template-columns: 5em 5em repeat(3, 1fr) 5em 5em 5em;
  background : {
    color: #0c0c0c;
  }

  &-content {
    @include gridarea($content-grid-area);
  }

  &-collapse {
    @include gridarea($collapse-grid-area);
    z-index: $collapse-layer;
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    justify-content: center;
  }

  &-sidebar {
    @include gridarea($sidebar-grid-area);
    z-index: $sidebar-layer;
  }

  &-brand {
    @include gridarea($brand-grid-area);
    z-index: $brand-layer;
    img {
      height: auto;
      width: 100%;
    }
  }
}
</style>
