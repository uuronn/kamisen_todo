<template>
  <div id="app">
    <div class="main">
      <h1 class="main__title">神の宣告</h1>
      <input
        class="main__input"
        v-model="TodoName"
        placeholder="taskName"
      />
      <button class="main__button" @click="addTodo">追加</button>
    </div>
    <Todos msg="Todos_file"/>
    <Option msg="option_file"/>
  </div>
</template>

<script>
import Option from './components/Option.vue';
import Todos from './components/Todos.vue';

export default {
  name: "main",
  data() {
    return {
    }
  },
  components: {
    Option,
    Todos
  },
  methods: {
    // todosに追加するメソッド
    addTodo() {
      if (this.TodoName) {
        this.todos.push(this.TodoName)
        this.TodoName = ""
      }
    },
  }
}
</script>

<style lang="scss" scoped>
  // .main {
  //   text-align: center;
  //   h1 {
  //     margin: 50px 0;
  //   }
  //   .main_input {
  //     width: 15vw;
  //     background: #fff;
  //   }
  //   .todos {
  //     width: 30vw;
  //     text-align: left;
  //     margin: 30px auto;
  //     padding-left: 300px;
  //     li{
  //       .hoge {
  //         width: 50%;
  //       }
  //     }
  //   }
  // }
</style>
