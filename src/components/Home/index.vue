<template>
  <div>
    <full-page ref="fullpage" :options="{}" id="fullpage">
      <div class="section">
        <landing></landing>
      </div>
      <div class="section">
        <projects></projects>
      </div>
    </full-page>
  </div>
</template>

<script>
import Landing from "./Landing";
import Projects from "./Projects";
export default {
  components: {
    Landing,
    Projects
  }
};
</script>