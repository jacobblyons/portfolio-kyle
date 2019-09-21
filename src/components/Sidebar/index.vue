<template>
  <div class="sidebar">
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
  }
};
</script>

<style lang="scss" scoped>
.sidebar {
  width: 100%;
  height: 100vh;
  background: {
    color: #eeca8b;
  }

  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  justify-content: center;
}
</style>