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
        @stopTodo="stopTodo"
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
      placeholder: "taskName",
    }
  },
  components: {
    Option,
    TodoList,
    Evaluation
  },
  methods: {
    // todosにタスクを追加するメソッド
    addTodo() {
      if (this.todoName) {
        this.todos.push({
          todoName: this.todoName,
          done: false,
          timer: 10,
          intervalTimer: null,
          timerOpen: false,
          startOpen: true,
          timerFinished: false
        })
        this.todoName = ""
      }
    },

    // メード切り替えメソッド
    changeModes(index) {
      this.placeholder = index
    },

    // 完了表示メソッド
    doneTodo(i) {
      this.todos[i].done = true
    },

    // タスク削除するメソッド
    deleteTodo(i) {
      clearInterval(this.todos[i].intervalTimer)
      this.todos.splice(i,1)
    },

    // タイマーを開始するメソッド
    startTodo(i) {
      this.todos[i].intervalTimer = setInterval(() => {
        this.todos[i].timer -= 1
      },1000)
      this.todos[i].startOpen  = false
      this.todos[i].timerOpen = true
    },

    stopTodo(i) {
      clearInterval(this.todos[i].intervalTimer);
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
      padding-left: 4px;
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
