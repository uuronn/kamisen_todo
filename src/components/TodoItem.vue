<template>
  <li>
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
      // TODO: emitで実装し直す
      this.todo.done = true
    },
    deleteTodo() {
      clearInterval(intervalTimer)
      // TODO: emitで実装し直す
      this.$destroy()
      this.$el.parentNode.removeChild(this.$el)
    },
    startTodo() {
      // TODO: emitで実装し直す
      if (this.todo.timer > 0) {
        intervalTimer = setInterval(() => {
          // TODO: emitで実装し直す
          this.todo.timer -= 1
        },1000)
      } else {
        confirm("test")
      }
        // TODO: emitで実装し直す
      this.todo.startOpen  = false
        // TODO: emitで実装し直す
      this.todo.timerOpen = true
    }
  }
}
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

  &__start {
    width: 48px;
    border: $button-border;
    border-radius: $button-radius;
    margin: $mg-2;
    background: #fff;

    &:hover {
      background: #fff;
    }
  }
}
</style>