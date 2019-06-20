<template>
  <div id="app">
    <div id="content">
      <router-view/>
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
};
</script>

<style lang="scss">
body {
  margin: 0;
  height: 100%;
}
#app {
  height: 100vh;
  display: grid;
  grid-template-columns: 7rem 1fr 1fr;
  grid-template-rows: 12rem 1fr 1fr;
  grid-template-areas:
    "content content content"
    "content content content"
    "content content content";

  background : {
    color: #0c0c0c;
  }
}

#content {
  grid-area: content;
}
</style>
