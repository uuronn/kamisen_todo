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
        @stopTimer="stopTimer"
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
    changeModes(value) {
      this.placeholder = value
    },

    // 完了表示メソッド
    doneTodo(index) {
      this.todos[index].done = true
    },

    // タスク削除するメソッド
    deleteTodo(index) {
      clearInterval(this.todos[index].intervalTimer)
      this.todos.splice(index, 1)
      this.resetActiveTimer()
    },

    // タイマーの初期化
    initTimer(index) {
      let decrementTimer = () => --this.todos[index].timer
      this.todos[index].intervalTimer = setInterval(decrementTimer, 1000)
    },

    // タイマーを開始するメソッド
    startTodo(index) {
      this.initTimer(index)
      this.todos[index].startOpen = false
      this.todos[index].timerOpen = true
    },

    // タイマーが０になった時の処理
    stopTimer(index) {
      clearInterval(this.todos[index].intervalTimer)
      this.todos[index].timerFinished = true
      alert("時間です！！！")
    },

    // ０になってない実行中のタイマーを全て初期化
    resetActiveTimer() {
      for(let i = 0; i < this.todos.length; i++) {
        if(this.todos[i].intervalTimer != null && !this.todos[i].timerFinished) {
          clearInterval(this.todos[i].intervalTimer)
          this.initTimer(i)
        }
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
