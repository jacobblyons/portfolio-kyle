<template>
  <div id="app">
    <router-view />
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
body {
  margin: 0;
  height: 100%;
}
#app {
  height: 100vh;
  background : {
    color: #0c0c0c;
  }
}

#content {
  grid-area: content;
}
</style>
