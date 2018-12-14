<template>
  <div class="todo-list-box">
    <div class="inputBox">
      <input type="checkbox" v-model="todoItem.complate" >
    </div>
    <div class="content-box" >
      <p>{{todoItem.content}}</p>
    </div>
    <button class="clearthis" @click="clearThis">X</button>
  </div>
</template>

 <script>
export default {
  name: "TodoList",
  data: function() {
    return {
      toggleStatus: false
    };
  },
  props: ["todoItem"],
  methods: {
    clearThis() {
      this.$emit("clearThis", this.todoItem.id);

    },
  }
};
</script>
<style scoped lang="scss">
.todo-list-box {
  border-bottom: 1px solid #b9b9b9;
  font-size: 24px;

  display: flex;

  overflow: hidden;
  .inputBox {
  }
  .content-box {
    width: 560px;
    margin-left: 46px;
    p {
      word-break: break-all;
      line-height: 2em;
    }
  }
}
</style>

