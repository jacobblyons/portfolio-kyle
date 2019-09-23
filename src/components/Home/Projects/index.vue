<template>
  <div class="projects">
    <img class="projects-background" src="@/assets/selected_work_background.jpg" />
    <p></p>
    <p></p>
    <p></p>
    <p></p>
    <p></p>
    <p></p>
    <p></p>
  </div>
</template>

<style lang="scss" scoped>
.projects {
  width: 100%;
  height: 100%;
  display: grid;
  grid-template-columns: repeat(10, 1fr);
  grid-template-rows: repeat(7, 1fr);

  &-background {
    grid-area: 1 / 1 / 6 / 11;
    height: 100%;
    object-fit: cover;
  }
}
</style>