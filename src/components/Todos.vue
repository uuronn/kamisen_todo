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

<script>
export default {
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
}
</script>

<style lang="scss" scoped>
.todos {
  &__container {
    background: green;
    .todos__list {
      background: red;
      .todos__check {
      }
      .todos__name {
        background: white;
      }
    }
  }
}
</style>
