<template>
  <div id="app">
    <div class="main">
      <h1 class="main__title">神の宣告</h1>
      <input
        class="main__input"
        v-model="todoName"
        :placeholder="placeholder"
      />
      <button class="main__add" @click="addTodo">追加</button>
      <TodoList :todos="todos" />
    </div>
    <Option @clickModes="placeholder = $event" />
    <Evaluation msg="Evaluation_file"/>
  </div>
</template>

<script>
import Option from './components/Option.vue'
import TodoList from './components/TodoList.vue'
import Evaluation from './components/Evaluation.vue'

export default {
  data() {
    return {
      todos: [],
      todoName: "",
      placeholder: " taskName",
    }
  },
  components: {
    Option,
    TodoList,
    Evaluation
  },
  methods: {
    addTodo() {
      if (this.todoName) {
        this.todos.push({
          todoName: this.todoName,
          done: false,
          timer: 10,
          timerOpen: false,
          startOpen: true
        })
        this.todoName = ""
      }
    }
  },
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
      margin: 5vw auto;
      font-size: 5vw;

      @media screen and (max-width: 720px) {
        margin: 24px auto 10vw auto;
        width: 10vw;
        font-size: 40px;
      }
    }

    &__input {
      width: 15vw;
      min-width: 196px;
      border-radius: 4px;
      border: 2px solid;
      margin: 2px;
      background: $button-back;

      &:hover {
        background: $button-hover;
      }
    }

    &__add {
      width: 48px;
      border-radius: 4px;
      border: 2px solid;
      margin: 2px;
      background: $button-back;

      &:hover {
        background: $button-hover;
      }

    }
  }
}
</style>
