<template>
  <div id="app">
    <navbar id="nav"></navbar>
    <vertical-label id="app-left" title="Introduction"></vertical-label>
    <div id="content">
      <router-view />
    </div>
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import VerticalLabel from "@/components/VerticalLabel.vue";

export default {
  components: {
    Navbar,
    VerticalLabel
  }
}
</script>

<style lang="scss">
body{
  margin: 0;
  height: 100%;
}
#app {
  height: 100vh;
  display: grid;
  grid-template-columns: 7em 1fr 1fr;
  grid-template-rows: 7rem 1fr 1fr;
  grid-template-areas: 
    "navbar navbar navbar"
    "left-area content content"
    "left-area content content";

  background : {
    color: #0c0c0c;
  }

  &-left {
    grid-area: left-area;
    height: 100%;
    width: 100%;
  }
}

#nav{
  grid-area: navbar;
}

#content {
  grid-area: content;
}
</style>
