<template>
  <div class="form-box">
    <div class="from-input">
      <input type="text" placeholder="接下去要做什么" autofocus="autofocus" @keyup.enter="addList">
    </div>
    <!-- <TodoListVue v-for="item in todoList" :key="item.id" :itemlist="item"></TodoListVue> -->
    <todo-list-vue
      v-for="(item, index) in todoList"
      :key="index"
      :todo-item="item"
      @clearThis="clearThis"
    ></todo-list-vue>
    <buttons-vue :todo-list="todoList" @passClearComplated="passClearComplated"></buttons-vue>
  </div>
</template>

<script>
import Vue from "vue";
import TodoListVue from "@/views/TodoList.vue";
import buttonsVue from "@/views/buttons.vue";

export default {
  name: "FormBox",
  components: {
    TodoListVue,
    buttonsVue
  },
  data() {
    return {
      todoList: [],
      id: 0,
      text: ""
    };
  },
  methods: {
    addList(e) {
      this.todoList.unshift({
        complate: false,
        content: e.target.value.trim(),
        id: this.id++
      });
      e.target.value = "";
    },
    /**@name 清除完成的项目 */
    passClearComplated() {
      this.todoList = [];
    },
    clearThis(data) {
      let oid = this.todoList.findIndex(item => item.id == data);
      this.todoList.splice(oid, 1);
      console.log(this.todoList);
    },
  }
};
</script>

<style lang="scss" scoped>
.form-box {
  width: 600px;
  background-color: #fff;
  margin: 0 auto;
  .from-input {
    border-bottom: 1px solid #b9b9b9;
    input {
      height: 50px;
      width: 100%;
      font-size: 24px;
    }
  }
  .botton-box {
  }
}
</style>