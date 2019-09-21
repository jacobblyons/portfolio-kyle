<template>
  <div @mouseover.stop="highlighted=true" @mouseleave.stop="highlighted=false" class="sidebar-link">
    <div>
      <span
        class="sidebar-link-title"
        :class="{'sidebar-link-title-highlighted':highlighted}"
      >{{title}}</span>
    </div>

    <div class="sidebar-link-children">
      <slot />
    </div>
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
.sidebar-link {
  display: flex;
  flex-flow: column nowrap;
  cursor: pointer;
  align-items: center;
  justify-content: flex-start;
  &-title {
    padding: {
      bottom: 0.1em;
    }
    font : {
      size: 1.8em;
      family: "komu-b";
      weight: 200;
    }
    letter-spacing: 0.2em;
    color: black;

    &-highlighted {
      color: white;
    }

    &-selected {
      color: grey;
      border-bottom: 3px solid white;
    }
  }

  &-children {
    margin: {
      top: 1em;
      bottom: 1em;
    }
  }
}
</style>