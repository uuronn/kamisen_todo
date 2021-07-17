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
        <button class="todos__done" @click="doneTodo">完了</button>
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
$todos-color: #fff;
$todos-border: 2px solid;
$todos-radius: 4px;
$todos-hover: #eee;
$todos-mg2: 2px;

.todos {
  &__container {

  }

  &__list {
    
  }

  &__check {
  }
  
  &__name {
    border-radius: $todos-radius;
    border: $todos-border;
    background: $todos-color;
    margin: $todos-mg2;
    text-align: center;

    &:hover {
      background: $todos-hover;
    }
  }

  &__done {
    border: $todos-border;
    border-radius: $todos-radius;
    background: $todos-color;
    margin: $todos-mg2;
    width: 48px;

    &:hover {
      background: $todos-hover;
    }
  }

  &__delete {
    border: $todos-border;
    border-radius: $todos-radius;
    background: $todos-color;
    margin: $todos-mg2;
    width: 48px;

    &:hover {
      background: $todos-hover;
    }
  }
}
</style>
