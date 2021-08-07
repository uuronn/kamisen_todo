<template>
  <div>
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
div {
  position: relative;
  overflow: hidden;
}
</style>
