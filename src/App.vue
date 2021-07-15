<template>
  <div id="app">
    <div class="main">
      <h1 class="main__title">神の宣告</h1>
      <input
        class="main__input"
        v-model="todoName"
        placeholder=" taskName"
      />
      <button class="main__button" @click="addTodo">追加</button>
      <Todos :todos="todos" />
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
  data() {
    return {
      todos: [],
      todoName: "",
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
      if (this.todoName) {
        this.todos.push(this.todoName)
        this.todoName = ""
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
      &__title {
        margin: 10vh 0;
        font-size: 4vw;
        font-family: 'HG正楷書体-PRO';
      }
      &__input,&__button {
        border: 1px solid;
        border-radius: 3px;
        background: #fff;
      }
    }
  }
</style>
