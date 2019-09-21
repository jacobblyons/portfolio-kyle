<template>
  <div
    @mouseover.stop="highlighted=true"
    @mouseleave.stop="highlighted=false"
    class="sidebar-link-child"
  >
    <span
      class="sidebar-link-child-title"
      :class="{'sidebar-link-child-title-highlighted':highlighted}"
    >{{title}}</span>
  </div>
</template>


<script>
export default {
  props: {
    title: String
  },
  data() {
    return {
      highlighted: false,
      selected: false
    };
  }
};
</script>

<style lang="scss" scoped>
.sidebar-link-child {
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  cursor: pointer;
  margin : {
    top: 1em;
    bottom: 1em;
  }

  &-title {
    padding: {
      bottom: 0.1em;
    }
    font: {
      size: 1.1em;
      family: "futura-pt";
      weight: 500;
    }
    color: black;

    &-highlighted {
      color: white;
    }

    &-selected {
      color: grey;
    }
  }
}
</style>