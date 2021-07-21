<template>
  <div class="todos">
    <ul class="todos__container">
      <li class="todos__list" v-for="(todo,i) in todos" :key="i">
        <span class="todos__span" v-show="todo.done">完了</span>
        <input
          class="todos__name"
          :value="todo.todoName"
          type="text"
        />
        <button class="todos__done" @click="doneTodo(i,todo.done)">完了</button>
        <button class="todos__delete" @click="deleteTodo(i)">削除</button>
        <button class="todos__start" @click="startTodo(i)">開始</button>{{ todo.time }}
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
      this.todos[i].done = true
    },

    // todosを削除するメソッド
    deleteTodo(i) {
      this.todos.splice(i,1)
      console.log(i)
    },

    // タスク開始ボタン
    startTodo(i) {
      if (this.todos[i].time > 0) {
        setTimeout(() => {
          this.todos[i].time -= 1
          this.startTodo(i)
        },1000)
      }
    }
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
