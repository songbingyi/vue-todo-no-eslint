<template>
  <div class="todo-list-box">
    <div class="circle"></div>
    <div class="content-box">
      <p>{{todoContent}}</p>
    </div>
  </div>
</template>

 <script>
import Vue from 'vue'; 

export default({
  data: function() {
    return{
       todoContent:'11的地方斯蒂芬斯蒂芬11的地方斯蒂芬斯蒂芬1'
    }
  },
  props: {
    itemList: {
      itemList
    },
  },
  mounted:function(){
    // console.log(itemList)
  }
});

// import Vue from 'vue';
// import Component from 'vue-class-component';

// @Component({
//   components: {}
// })
// export default class notYetDone extends Vue {

// }

</script>






<style scoped lang="scss">
.todo-list-box {
  border-bottom: 1px solid #b9b9b9;
  font-size: 24px;
  position: relative;
  min-height: 60px;
  overflow: hidden;
  .circle {
    width: 30px;
    height: 30px;
    border: 1px solid #303030;
    border-radius: 50%;
    position: absolute;
    top: 10px;
    left: 5px;
  }
  .content-box {
    width: 560px;
    margin-left: 46px;
    margin-top: 10px;
    p {
      word-break: break-all;
    }
  }
}
</style>

