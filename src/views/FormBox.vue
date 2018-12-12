<template>
  <div class="form-box">
    <div class="from-input">
      <input type="text" placeholder="接下去要做什么" autofocus="autofocus">
    </div>
    <TodoListVue v-for="item in todoList" :key="item.id" :item-list="item"></TodoListVue>
    <div class="botton-box">
      <NotYetDoneVue></NotYetDoneVue>
      <ChooseBoxVue></ChooseBoxVue>
      <ComplatedBtnVue></ComplatedBtnVue>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import TodoListVue from "@/views/TodoList.vue";
import NotYetDoneVue from "@/views/NotYetDone.vue";
import ComplatedBtnVue from "@/views/ComplatedBtn.vue";
import ChooseBoxVue from "@/views/ChooseBox.vue";

export default {
  name: "FormBox",
  components: {
    TodoListVue,
    NotYetDoneVue,
    ComplatedBtnVue,
    ChooseBoxVue
  }
};
data: {
  todoList: [
    {
      status: true,
      content: "第一个todo"
    }
  ];
}
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
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 0 20px;
    .not-yet-done {
      // flex: 1;
    }
    .choose-box {
      // flex: 1;
    }
    .complated-btn {
      // flex: 1;
    }
  }
}
</style>