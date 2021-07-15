<template>
  <div id="app">
    <div class="main">
      <h1 class="main__title">神の宣告</h1>
      <input
        class="main__input"
        v-model="TodoName"
        placeholder=" taskName"
      />
      <button class="main__button" @click="addTodo">追加</button>
      <Todos msg="Todos_file" />
    </div>
    <Option msg="option_file" />
    <Evaluation msg="Evaluation_file"/>
  </div>
</template>

<script>
import Option from './components/Option.vue'
import Todos from './components/Todos.vue'
import Evaluation from './components/Evaluation.vue'

export default {
  name: "main",
  data() {
    return {
      TodoName: "",
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

<style lang="scss">
  #app {
    height: 100vh;
    position: relative;
    overflow: hidden;
    .main {
      text-align: center;
      .main__title {
        margin: 10vh 0;
        font-size: 4vw;
        font-family: 'HG正楷書体-PRO';
      }
      .main__input,.main__button {
        border: 1px solid;
        border-radius: 3px;
        background: #fff;
      }
    }
  }
</style>
