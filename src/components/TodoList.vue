<template>
  <div class="todos">
    <ul class="todos__container">
      <Todo
        class="todos__list"
        v-for="(todo, i) in todos"
        :key="i"
        :todo="todo"
        :index='i'
        @doneTodo='doneTodo'
        @deleteTodo='deleteTodo'
        @startTodo='startTodo'
      />
    </ul>
  </div>
</template>

<script>
import Todo from './TodoItem.vue'

let intervalTimer

export default {
  components: {
    Todo
  },
  props: [
    'todos'
  ],
  methods: {
    doneTodo(i) {
      this.todos[i].done = true
    },
    deleteTodo(i) {
      clearInterval(intervalTimer)
      this.todos.splice(i, 1)
    },
    startTodo(i) {
      if (this.todos[i].timer > 0) {
        intervalTimer = setInterval(() => {
          this.todos[i].timer -= 1
        },1000)
      } else {
        confirm("test")
      }
      this.todos[i].startOpen  = false
      this.todos[i].timerOpen = true
    }
  }
}
</script>
