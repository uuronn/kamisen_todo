<template>
  <div class="root">
    <TheTitle/>
    <TodoInput/>
    <OptionButton @clickModes="changeModes"/>
    <TheEvaluation/>
  </div>
</template>

<script>
import TheTitle from './components/TheTitle.vue'
import TodoInput from './components/TodoInput.vue'
import OptionButton from './components/OptionButton.vue'
import TheEvaluation from './components/TheEvaluation.vue'

export default {
  components: {
    TheTitle,
    TodoInput,
    OptionButton,
    TheEvaluation
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
.root {
  min-height: 100vh;
  position: relative;
  overflow: hidden;
  background: #CC1669;
}
</style>
