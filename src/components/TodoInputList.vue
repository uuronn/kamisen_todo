<template>
  <div class="todoInputList">
    <ul class="todoInputList__content">
      <TodoInputListItem
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
import TodoInputListItem from './TodoInputListItem.vue'

export default Vue.extend({
  props: {
    todos: Array,
  },
  components: {
    TodoInputListItem
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
