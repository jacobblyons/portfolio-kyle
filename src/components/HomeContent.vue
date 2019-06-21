<template>
  <div class="home-content">
    <div class="home-content-name">KYLE RHODES</div>
    <div class="home-content-titles">
      <div class="home-content-titles-indent-line">
        <svg height="75" width="9">
          <line x1="0" y1="0" x2="0" y2="75" style="stroke:#eeca8b;stroke-width:9"></line>
        </svg>
      </div>
      <div class="home-content-titles-text-container">
        <div class="home-content-titles-text">Graphic Design</div>
        <div class="home-content-titles-text">UI / UX Design</div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.home-content {
  display: flex;
  flex-flow: column nowrap;
  align-items: flex-start;
  justify-content: center;
  &-name {
    color: #eeca8b;
    font: {
      size: 4em;
    }
  }

  &-titles {
    height: 10em;
    display: flex;
    flex-flow: row nowrap;
    align-items: center;
    justify-content: flex-start;

    &-indent-line {
      padding: {
        right: 2rem;
      }
    }
    &-text {
      color: white;
      font: {
        size: 2em;
      }
      &-container {
        display: flex;
        flex-flow: column nowrap;
        align-items: flex-start;
        justify-content: space-around;
      }
    }
  }
}
</style>
