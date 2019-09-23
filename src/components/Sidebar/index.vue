<template>
  <div class="sidebar" :class="{'sidebar-closed':!opened}">
    <sidebar-link title="intro" />
    <sidebar-link title="work">
      <sidebar-link-child title="Indispose"></sidebar-link-child>
      <sidebar-link-child title="Red Twig"></sidebar-link-child>
      <sidebar-link-child title="Seattle Ridge"></sidebar-link-child>
      <sidebar-link-child title="Insight"></sidebar-link-child>
    </sidebar-link>
    <sidebar-link title="contact" />
    <sidebar-link title="about" />
  </div>
</template>

<script>
import SidebarLink from "./SidebarLink";
import SidebarLinkChild from "./SidebarLinkChild";
export default {
  components: {
    SidebarLink,
    SidebarLinkChild
  },
  props: {
    opened: Boolean
  }
};
</script>

<style lang="scss" scoped>
.sidebar {
  width: 100%;
  height: 100vh;
  transition: 0.3s;
  background: {
    color: #eeca8b;
  }
  overflow-x: hidden;

  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  justify-content: center;

  &-closed {
    width: 300%;
    margin-left: 100%;
  }
}
</style>