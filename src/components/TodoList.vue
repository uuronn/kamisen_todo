<template>
  <div class="todos">
    <ul class="todos__container">
      <TodoItem v-for="(todo,i) in todos" :todo="todo" :key="i" :i="i" @test="doneAction2" />
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
    doneAction2(i) {
      this.$emit("click",i)
    }
  }
})
</script>

<style lang="scss" scoped>

</style>
