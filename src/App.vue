<template>
  <div id="app">
    <MainTitle/>
    <TodoInput/>
    <Option @clickModes="changeModes"/>
    <Evaluation msg="Evaluation_file"/>
  </div>
</template>

<script>
import MainTitle from './components/MainTitle.vue'
import TodoInput from './components/TodoInput.vue'
import Option from './components/Option.vue'
import Evaluation from './components/Evaluation.vue'

export default {
  data() {
    return {
      todos: [],
      todoName: "",
      placeholder: "taskName",
    }
  },
  components: {
    MainTitle,
    TodoInput,
    Option,
    Evaluation
  },
  methods: {
    // モード切り替えメソッド
    changeModes(index) {
      this.placeholder = index
    }
  }
}
</script>

<style lang="scss" scoped>
#app {
  height: 100vh;
  position: relative;
  overflow: hidden;

  .main {
    text-align: center;

    &__input {
      width: 15vw;
      min-width: 196px;
      padding-left: 4px;
      border-radius: 4px;
      border: 2px solid;
      margin: 2px;
      background: $button-back;

      &:hover {
        background: $button-hover;
      }
    }

    &__add {
      width: 48px;
      border-radius: 4px;
      border: 2px solid;
      margin: 2px;
      background: $button-back;

      &:hover {
        background: $button-hover;
      }
    }
  }
}
</style>
