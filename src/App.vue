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
      <TodoList
        :todos="todos"
        @clickDone="doneTodo"
        @clickDelete="deleteTodo"
        @clickStart="startTodo"
      />
    </div>
    <Option @clickModes="changeModes"/>
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
          intervalTimer: null,
          timerOpen: false,
          startOpen: true,
          doneBtnShow: true
        })
        this.todoName = ""
      }
    },
    changeModes(index) {
      this.placeholder = index
    },
    doneTodo(i) {
      this.todos[i].done = true
      this.todos[i].doneBtnShow = false
    },
    deleteTodo(i) {
      this.todos.splice(i,1)
      // clearInterval(this.todos[i].intervalTimer)
    },
    startTodo(i) {
      this.todos[i].intervalTimer = setInterval(() => {
        this.todos[i].timer -= 1
      },1000)
      this.todos[i].startOpen  = false
      this.todos[i].timerOpen = true
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
