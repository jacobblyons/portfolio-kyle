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
  display: flex;
  flex-flow: row nowrap;
  align-items: flex-start;
  justify-content: space-between;
  color: white;

  &-brand {
    padding: {
      top: 0rem;
      left: 5rem;
      right: 2rem;
      bottom: 1rem;
    }
  }

  &-brand-icon {
    width: 5rem;
    height: auto;
  }

  &-collapse {
    padding: {
      top: 1rem;
      left: 2rem;
      right: 2rem;
      bottom: 1rem;
    }
  }
}
</style>
