<template>
  <div class="todos">
    <ul class="todos__container">
      <li class="todos__list" v-for="(todo,i) in todos" :key="i">
        <span v-if="todo.test">{{ "完了" }}</span>
        <input class="todos__check" type="checkbox">
        <input
          class="todos__name"
          :value="todo.todoName"
          type="text"
        />
        <button class="todos__done" @click="doneTodo(i,todo.test)">完了</button>
        <button class="todos__delete" @click="deleteTodo(i)">削除</button>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    todos: Array,
  },
  methods: {

    // 完了を表示させるメソッド
    doneTodo(i) {
    this.todos[i].test = true
  },

    // todosを削除するメソッド
    deleteTodo(i) {
      this.todos.splice(i,1)
      console.log(i)
    },
  }
})
</script>

<style lang="scss" scoped>
.todos {
  &__name {
    border-radius: $button-radius;
    border: $button-border;
    text-align: center;
    margin: $mg-2;
    background: #fff;

    &:hover {
      background: $button-hover;
    }
  }

  &__done {
    width: 48px;
    border: $button-border;
    border-radius: $button-radius;
    margin: $mg-2;
    background: #fff;

    &:hover {
      background: $button-hover;
    }
  }

  &__delete {
    width: 48px;
    border: $button-border;
    border-radius: $button-radius;
    margin: $mg-2;
    background: #fff;

    &:hover {
      background: $button-hover;
    }
  }
}
</style>
