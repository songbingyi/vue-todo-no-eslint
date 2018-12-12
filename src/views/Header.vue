<template>
  <div class="home">
    <h1>
      {{ title }}
    </h1>
  </div>
</template>

<script lang="ts">

import Vue from "vue";

export default Vue.extend({
  name: "Header",
  components: {},
  data:function(){
    return{
      title:'Ftodo vue'
    }
  }
});
</script>

<style lang="scss" scpoed>
.home {
  color: aqua;
  text-align: center;
}
</style>