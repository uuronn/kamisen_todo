<template>
  <div class="todoInput">
    <input
      class="todoInput__form"
      v-model="todoName"
      :placeholder="placeholder"
    />
    <button class="todoInput__button" @click="addTodo">追加</button>
    <TodoInputList
      :todos="todos"
      @doneTodo="doneTodo"
      @deleteTodo="deleteTodo"
      @startTodo="startTodo"
      @stopTodo="stopTodo"
    />
  </div>
</template>

<script>
import TodoInputList from './TodoInputList.vue'

export default {
  data() {
    return {
      todoName: "",
      placeholder: " taskName",
      todos: [],
    }
  },
  components: {
    TodoInputList
  },
  methods: {
    // タスクを追加するメソッド
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

    // タスク完了表示するメソッド
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

    // タイマー停止するメソッド
    stopTodo(i) {
      clearInterval(this.todos[i].intervalTimer);
    }
  },
}
</script>

<style lang="scss" scoped>
.todoInput {
  text-align: center;

  // タスク名入れるinput
  &__form {
    width: 15vw;
    min-width: 196px;
    border-radius: 4px;
    border: 2px solid;
    margin: 2px;
    background: #fff;

    &:hover {
      background: $button-hover;
    }
  }

  &__button {
    width: 48px;
    border: 2px solid;
    border-radius: 4px;
    margin: 2px;
    background: $button-back;
    
    &:hover {
      background: $button-hover;
    }
  }
}
</style>
