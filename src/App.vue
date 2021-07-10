<template>
  <div id="app">
    <div class="main">
      <h1>神の宣告</h1>
      <input v-model="TodoName" placeholder="taskName">
      <button @click="addTodo">追加</button>
      <ul class="todos">
        <li v-for="(todo,i) in todos" :key="i">
          <input type="checkbox">
          <span>{{ todo }}</span>
          <button clss="todos_button" @click="doneTodo">完了</button>
          <button class="todos_button" @click="deleteTodo(i)">削除</button>
        </li>
      </ul>
    </div>
    
    <Option msg="optionPage"/>
  </div>
</template>

<script>
import Option from './components/Option.vue';

export default {
  name: "main",
  data() {
    return {
      todos: [],
    }
  },
  components: {
    Option
  },
  methods: {
    // todosにタスクを追加するメソッド
    addTodo() {
      if (this.TodoName) {
        this.todos.push(this.TodoName)
        this.TodoName = ""
      }
    },
    // 未実装
    doneTodo() {
      
    },
    // todosのタスクを削除するメソッド
    deleteTodo(i) {
      this.todos.splice(i,1)
    }
  }
}
</script>

<style>
  #app {
    display: flex;
    justify-content: center;
  }

  .main {
    flex-flow: column;
    text-align: center;
  }
  
  h1 {
    padding: 30px 0;
  }

  .todos {
    text-align: left;
  }
</style>
