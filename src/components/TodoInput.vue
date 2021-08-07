<template>
  <div class="todo">
    <input
      class="todo__input"
      v-model="todoName"
      :placeholder="placeholder"
    />
    <button class="todo__button" @click="addTodo">追加</button>
    <TodoList
      :todos="todos"
      @donteTodo="doneTodo"
      @deleteTodo="deleteTodo"
      @startTodo="startTodo"
      @stopTodo="stopTodo"
    />
  </div>
</template>

<script>
import TodoList from './TodoList.vue'

export default {
  data() {
    return {
      todoName: "",
      placeholder: " taskName",
      todos: [],
    }
  },
  components: {
    TodoList
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
.todo {
  text-align: center;

  // タスク名入れるinput
  &__input {
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
}
</style>
