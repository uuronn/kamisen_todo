<template>
  <div id="app">
    <div class="main">
      <h1 class="main__title">神の宣告</h1>
      <input
        class="main__input"
        v-model="todoName"
        :placeholder="placeholder"
      />
      <button class="main__add" @click="addTodo">追加</button>
      <Todos :todos="todos" />
    </div>
    <Option @clickModes="placeholder = $event" />
    <Evaluation msg="Evaluation_file"/>
  </div>
</template>

<script>
// @clickTest="doneShow = $event"
import Option from './components/Option.vue'
import Todos from './components/Todos.vue'
import Evaluation from './components/Evaluation.vue'

export default {
  data() {
    return {
      todos: [],
      todoName: "",
      placeholder: " taskName",
    }
  },
  components: {
    Option,
    Todos,
    Evaluation
  },
  methods: {
    // todosに追加するメソッド
    addTodo() {
      // const timeMessage = "時間切れ"
      // function announceTime() {
      //   confirm(timeMessage)
      // }

      if (this.todoName) {
        this.todos.push({
          todoName: this.todoName,
          // doneShow: false
        })

        this.todoName = ""
        // setTimeout(announceTime,1000)
      }
    }
  },
}
</script>

<style lang="scss">
#app {
  height: 100vh;
  position: relative;
  overflow: hidden;

  .main {
    text-align: center;

    &__title {
      margin: 5vw auto;
      font-size: 5vw;
      font-family: 'HG正楷書体-PRO';

      @media screen and (max-width: 720px) {
        margin: 24px auto 10vw auto;
        width: 10vw;
        font-size: 40px;
      }
    }

    &__input {
      width: 15vw;
      min-width: 196px;
      border-radius: $button-radius;
      border: $button-border;
      margin: $mg-2;
      background: #fff;

      &:hover {
        background: $button-hover;
      }
    }

    &__add {
      width: 48px;
      border-radius: $button-radius;
      border: $button-border;
      margin: $mg-2;
      background: #fff;
      
      &:hover {
        background: $button-hover;
      }
    }
  }
}
</style>
