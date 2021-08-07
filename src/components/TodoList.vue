<template>
  <div class="todos">
    <ul class="todos__container">
      <TodoListItem
        v-for="(todo,i) in todos"
        :todo="todo"
        :key="i"
        @doneTodo="doneTodo(i)"
        @deleteTodo="deleteTodo(i)"
        @startTodo="startTodo(i)"
        @stopTodo="stopTodo(i)"
      />
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import TodoListItem from './TodoListItem.vue'

export default Vue.extend({
  props: {
    todos: Array,
  },
  components: {
    TodoListItem
  },
  methods: {
    doneTodo(i) {
      this.$emit("doneTodo",i)
    },
    deleteTodo(i) {
      this.$emit("deleteTodo",i)
    },
    startTodo(i) {
      this.$emit("startTodo",i)
    },
    stopTodo(i) {
      this.$emit("stopTodo",i)
      alert("test")
    }
  }
})
</script>
