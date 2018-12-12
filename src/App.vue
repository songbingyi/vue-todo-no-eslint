<template>
  <div id="app">
    <div class="cover"></div>
    <Header></Header>
    <formBoxVue></formBoxVue>
  </div>
</template>
<script lang="ts">

import Vue from "vue";

import Header from "@/views/Header.vue";
import FormBoxVue from "@/views/FormBox.vue";

export default({
  components: {
    Header,
    FormBoxVue,
  }
});
</script>

<style lang="scss">
#app {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
}

.cover {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  opacity: 0.4;
  background-color: rgb(17, 17, 17);
  z-index: -1;
}
</style>
