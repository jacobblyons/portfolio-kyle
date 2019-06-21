<template>
  <div class="vertical-label">
    <div class="vertical-label-line">
      <svg height="40" width="5">
        <line x1="0" y1="0" x2="0" y2="40" style="stroke:rgb(255,255,255);stroke-width:9"></line>
      </svg>
    </div>
    <div>
      <p class="vertical-label-text">{{title}}</p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.vertical-label {
  width: 100%;
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  justify-content: flex-start;
  width: 5rem;
  &-text {
    color: white;
    font: {
      size: 2.5em;
    }
    writing-mode: vertical-rl;
    text-orientation: sideways;
  }
}
</style>

<script>
export default {
  name: "vertical-label",
  props: {
    title: String
  }
};
</script>

