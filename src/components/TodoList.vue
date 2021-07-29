<template>
  <div class="todos">
    <ul class="todos__container">
      <TodoItem
        v-for="(todo,i) in todos"
        :todo="todo"
        :key="i"
        @clickDone="doneTodo(i)"
        @clickDelete="deleteTodo(i)"
        @clickStart="startTodo(i)"
      />
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import TodoItem from './TodoItem.vue'

export default Vue.extend({
  props: {
    todos: Array,
  },
  components: {
    TodoItem
  },
  methods: {
    doneTodo(i) {
      this.$emit("clickDone",i)
    },
    deleteTodo(i) {
      this.$emit("clickDelete",i)
    },
    startTodo(i) {
      this.$emit("clickStart",i)
    }
  }
})
</script>
