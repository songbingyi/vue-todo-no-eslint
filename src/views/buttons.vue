<template>
  <div class="buttons">
    <div>{{no}} items left</div>
    <div class="choose-state">
      <button
        v-for="(state, index) in stateButtons"
        :key="index"
        :class="['button-all',currentBtn == state ? 'choosen':'']"
        @click="chooseBtn(state)"
      >{{state}}</button>
    </div>
    <div>
      <button class="complated">complated</button>
    </div>
  </div>
</template>

<script lang='ts'>
export default {
  name: "buttons",
  data() {
    return {
      no: "1",
      stateButtons: ["all", "active", "complated"],
      currentBtn: {}
    };
  },
  methods: {
    chooseBtn: function(state: string) {
      this.currentBtn = state;
    }
  }
};
</script>

<style lang="scss" scoped>
.buttons {
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 20px;
  .choose-state {
    width: 200px;
    display: flex;
    justify-content: space-between;
    .button-all {
      border-radius: 1px;
      outline: 0;
    }
    .choosen {
      border: 1px solid red;
    }
  }
}
</style>