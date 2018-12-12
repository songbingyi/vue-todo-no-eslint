<template>
  <div class="not-yet-done">{{leftItems}} items left</div>
</template>

<script lang='ts'>
import Vue from 'vue';


export default Vue.extend({
  name: "not-yet-done",
});
</script>

<style lang="scss" scoped>
.not-yet-done {
  // flex: 1;
}
</style>