<template>
  <div class="todos">
    <ul class="todos__container">
      <TodoItem msg="hello" v-for="(todo,i) in todos" :todo="todo" :key="i"/>
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
  }
})
</script>

<style lang="scss" scoped>

</style>
