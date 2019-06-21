<template>
  <div class="navbar">
    <div class="navbar-brand">
      <img class="navbar-brand-icon" src="../assets/Asset 6.png">
    </div>
    <div class="navbar-collapse">COL</div>
  </div>
</template>

<style lang="scss" scoped>
.navbar {
  width: 100%;
  height: 100%;
  display: grid;
  grid-template-columns: repeat(6, 1fr);
  grid-template-rows: auto;
  grid-template-areas: "brand . . .  . col";
  color: white;

  &-brand {
    grid-area: brand;
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
    justify-content: flex-start;
  }

  &-brand-icon {
    width: 5rem;
    height: auto;
  }

  &-collapse {
    grid-area: col;
    padding: {
      top: 1rem;
      left: 2rem;
      right: 2rem;
      bottom: 1rem;
    }
  }
}
</style>
