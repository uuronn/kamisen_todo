<template>
  <div class="todos">
    <ul class="todos__container">
      <li class="todos__list" v-for="(todo,i) in todos" :key="i">
        <input class="todos__check" type="checkbox">
        <input
          class="todos__name"
          :value="todo"
          type="text"
        />
        <button clss="todos__done" @click="doneTodo">完了</button>
        <button class="todos__delete" @click="deleteTodo(i)">削除</button>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    todos: Array
  },
  methods: {
    doneTodo() {

    },
    // todosを削除するメソッド
    deleteTodo(i) {
      this.todos.splice(i,1)
    }
  },
  data() {
    return {
      num: ''
    }
  }
})
</script>

<style lang="scss" scoped>
$todos__color: #fff;
$todos__border: 1px solid;
$todos__radius: 3px;

.todos {
  &__container {

  }

  &__list {
    
  }

  &__check {
  }
  
  &__name {
    border-radius: $todos__radius;
    border: $todos__border;
    background: $todos__color;
  }
}
</style>
