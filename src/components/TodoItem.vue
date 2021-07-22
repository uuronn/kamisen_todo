<template>
  <li>
    <span class="todos__span" v-if="todo.done">完了</span>
    <input
      class="todos__name"
      :value="todo.todoName"
      type="text"
    />
    <button class="todos__done" @click="$emit('doneTodo', index)">完了</button>
    <button class="todos__delete" @click="$emit('deleteTodo', index)">削除</button>
    <button class="todos__start" v-if="todo.startOpen" @click="$emit('startTodo', index)">開始</button>
    <span class="todos__timer" v-if="todo.timerOpen">{{ todo.timer }}</span>
  </li>
</template>

<script>
export default {
  props: [
    'todo',
    'index'
  ]
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
