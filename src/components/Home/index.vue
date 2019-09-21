<template>
  <div>
    <full-page ref="fullpage" :options="{}" id="fullpage">
      <div class="section">
        <landing></landing>
      </div>
      <div class="section">Second section ...</div>
    </full-page>
  </div>
</template>

<script>
import Landing from "./Landing";
export default {
  components: {
    Landing
  }
};
</script>