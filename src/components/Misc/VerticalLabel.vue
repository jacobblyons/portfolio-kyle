<template>
  <div class="vertical-label">
    <div class="vertical-label-line">
      <svg height="55" width="5">
        <line x1="0" y1="0" x2="0" y2="40" style="stroke:rgb(255,255,255);stroke-width:9" />
      </svg>
    </div>
    <div>
      <p class="vertical-label-text">{{title}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "vertical-label",
  props: {
    title: String,
    lineThickness: Number
  }
};
</script>

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
      size: 2em;
      family: "komu-b";
    }
    letter-spacing: 0.4em;
    writing-mode: vertical-rl;
    text-orientation: sideways;
  }
}
</style>


