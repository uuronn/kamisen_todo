<template>
  <div class="todos">
    <ul class="todos__container">
      <Todo
        class="todos__list"
        v-for="(todo, index) in todos"
        :key="index"
        :todo="todo"
        :index='index'
        @doneTodo='doneTodo'
        @deleteTodo='deleteTodo'
        @startTodo='startTodo'
      />
    </ul>
  </div>
</template>

<script>
import Todo from './TodoItem.vue'

export default {
  components: {
    Todo
  },
  props: {
    todos: {
      type     : Array,
      require  : false,
      'default': []
    }
  },
  methods: {
    doneTodo(index) {
      this.$emit('doneTodo', index)
    },
    deleteTodo(index) {
      this.$emit('deleteTodo', index)
    },
    startTodo(index) {
      this.$emit('startTodo', index)
    }
  }
}
</script>
