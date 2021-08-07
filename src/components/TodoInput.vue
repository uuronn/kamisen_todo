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
      @clickDone="doneTodo"
      @clickDelete="deleteTodo"
      @clickStart="startTodo"
      @stopTodo="stopTodo"
    />
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [],
      todoName: "",
      placeholder: "taskName",
    }
  },
  components: {
    Title,
    TodoList,
    Option,
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
