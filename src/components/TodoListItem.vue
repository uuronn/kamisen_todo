<template>
  <div class="todos__list">
    <span class="todos__span" v-if="todo.done">完了</span>
    <input
      class="todos__name"
      :value="todo.todoName"
      type="text"
    />
    <button class="todos__done" v-if="!todo.done" @click="doneTodo">完了</button>
    <button class="todos__delete" @click="deleteTodo">削除</button>
    <button class="todos__start" v-if="todo.startOpen" @click="startTodo">開始</button>
    <span class="todos__timer" v-if="todo.timerOpen">{{ todo.timer }}</span>
  </div>
</template>

<script>
export default {
  props: {
    todo: Object,
  },
  methods: {
    // 完了ボタンを表示させるメソッド
    doneTodo() {
      this.$emit("doneTodo")
    },

    // todosを削除するメソッド
    deleteTodo() {
      this.$emit("deleteTodo")
    },

    // タイマー開始ボタン
    startTodo() {
      this.$emit("startTodo")
    }
  },
  watch: {
    todo: {
      handler: function() {
        if(this.todo.timer === 0) {
          this.$emit("stopTodo");

          
        }
      },
      deep: true
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
