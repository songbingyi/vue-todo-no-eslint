<template>
  <div class="buttons">
    <div>{{unFinishedTodo}} items left</div>
    <div class="choose-state">
      <button
        v-for="(state, index) in stateButtons"
        :key="index"
        :class="['button-all',filter == state ? 'choosen':'']"
        @click="toggle(state)"
      >{{state}}</button>
    </div>
    <div>
      <button class="complated" @click="clearComplated">clear complated</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "buttons",
  data() {
    return {
      no: "1",
      stateButtons: ["all", "active", "complated"],
    };
  },
  props:{
    todoList: {
      type: Array
    },
    filter: {
      type: String
    }
  },
  methods: {
    toggle: function(state) {
 
      this.$emit('chooseState',state)
    },
    clearComplated () {
      this.$emit('passClearComplated')
    }
  },
  computed: {
    unFinishedTodo() {
      return this.todoList.filter(
        item => item.complate == false
      ).length
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
      outline: 0;
    }
    .choosen {
      border: 1px solid red;
    }
  }
}
</style>