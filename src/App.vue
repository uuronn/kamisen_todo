<template>
  <div id="app">
    <div class="main">
      <h1 class="main__title">神の宣告</h1>
      <input
        class="main__input"
        v-model="TodoName"
        placeholder="taskName"
      />
      <button class="main__button" @click="addTodo">追加</button>
      <Todos msg="Todos_file"/>
    </div>
    <Option msg="option_file"/>
    <Evaluation msg="Evaluation_file"/>
  </div>
</template>

<script>
import Option from './components/Option.vue';
import Todos from './components/Todos.vue';
import Evaluation from './components/Evaluation.vue'

export default {
  name: "main",
  props: {

  },
  data() {
    return {

    }
  },
  components: {
    Option,
    Todos,
    Evaluation
  },
  methods: {
    // todosに追加するメソッド
    addTodo() {
      if (this.TodoName) {
        this.todos.push(this.TodoName)
        this.TodoName = ""
      }
    },
  }
}
</script>

<style lang="scss" scoped>
  #app {
    height: 100%;
    position: relative;
    overflow: hidden;
    .main {
      text-align: center;
    }
  }
    // display: flex;
    // justify-content: space-between;
    // margin-left: auto;
    // width: 55vw;
    // position: relative;
    // overflow: hidden;

    // .right {
    //   position: absolute;
    //   right: 0;
    // }
  // .main {
  //   text-align: center;
  //   h1 {
  //     margin: 50px 0;
  //   }
  //   .main_input {
  //     width: 15vw;
  //     background: #fff;
  //   }
  //   .todos {
  //     width: 30vw;
  //     text-align: left;
  //     margin: 30px auto;
  //     padding-left: 300px;
  //     li{
  //       .hoge {
  //         width: 50%;
  //       }
  //     }
  //   }
  // }
</style>
