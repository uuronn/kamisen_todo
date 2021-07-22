<template>
  <div class="todos">
    <ul class="todos__container">
      <Todo class="todos__list" v-for="(todo, i) in todos" :todo="todo" :key="i" />
    </ul>
  </div>
</template>

<script>
import Todo from './Todo.vue'

export default {
  components: {
    Todo
  },
  props: {
    todos: Array,
  }
}
</script>

<style lang="scss" scoped>

</style>
