<template>
  <li class="todos__list">
    <span class="todos__span" v-if="todo.done">完了</span>
    <input
      class="todos__name"
      :value="todo.todoName"
      type="text"
    />
    <button class="todos__done" @click="doneTodo">完了</button>
    <button class="todos__delete" @click="deleteTodo">削除</button>
    <button class="todos__start" v-if="todo.startOpen" @click="startTodo">開始</button>
    <span class="todos__timer" v-if="todo.timerOpen">{{ todo.timer }}</span>
  </li>
</template>

<script>
let intervalTimer

export default {
  props: {
    todo: {}
  },
  methods: {
    doneTodo() {
      this.todo.done = true
    },

    // todosを削除するメソッド
    deleteTodo() {
      clearInterval(intervalTimer)
      this.$destroy();
      this.$el.parentNode.removeChild(this.$el)
    },

    // タイマー開始ボタン
    startTodo() {
      intervalTimer = setInterval(() => {
        this.todo.timer -= 1
      },1000)
      this.todo.startOpen  = false
      this.todo.timerOpen = true
    }
  }
}
</script>

<style lang="scss" scoped>
.todos {
  &__name {
    border-radius: 4px;
    border: 2px solid;
    text-align: center;
    margin: 2px;
    background: $button-back;

    &:hover {
      background: $button-hover;
    }
  }

  &__done {
    width: 48px;
    border: 2px solid;
    border-radius: 4px;
    margin: 2px;
    background: $button-back;

    &:hover {
      background: $button-hover;
    }
  }

  &__delete {
    width: 48px;
    border: 2px solid;
    border-radius: 4px;
    margin: 2px;
    background: $button-back;

    &:hover {
      background: $button-hover;
    }
  }

  &__start {
    width: 48px;
    border: 2px solid;
    border-radius: 4px;
    margin: 2px;
    background: $button-back;

    &:hover {
      background: $button-hover;
      }
  }
}
</style>
