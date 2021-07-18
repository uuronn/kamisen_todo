<template>
  <div id="app">
    <div class="main">
      <h1 class="main__title">神の宣告</h1>
      {{ parent_num }}
      <input
        class="main__input"
        v-model="todoName"
        :placeholder="placeholder"
      />
      <button class="main__add" @click="addTodo">追加</button>
      <Todos :todos="todos"/>
    </div>
    <Option @changePlaceholder="changePlaceholder" />
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
      placeholder: "taskName"
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
    changePlaceholder(value) {
      this.placeholder = value
    }
  }
}
</script>

<style lang="scss">
// @import "./src/assets/scss/common.scss";
$main-color: #fff;
$main-border: 2px solid;
$main-radius: 4px;
$main-hover: #eee;
$main-mg2: 2px;

#app {
  height: 100vh;
  position: relative;
  overflow: hidden;

  .main {
    text-align: center;

    &__title {
      margin: 5vw auto;
      font-size: 5vw;
      font-family: 'HG正楷書体-PRO';

      @media screen and (max-width: 720px) {
        margin: 24px auto 10vw auto;
        width: 10vw;
        font-size: 40px;
      }
    }

    &__input {
      border: $main-border;
      border-radius: $main-radius;
      background: $main-color;
      margin: $main-mg2;
      width: 15vw;
      min-width: 196px;

      &:hover {
        background: #eee;
      }
    }

    &__add {
      border: $main-border;
      border-radius: $main-radius;
      background: $main-color;
      margin: $main-mg2;
      width: 48px;
      
      &:hover {
        background: #eee;
      }
    }
  }
}
</style>
