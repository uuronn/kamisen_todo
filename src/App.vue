<template>
  <div class="root">
    <Title/>
    <TodoInput/>
    <Option @placeholderChange="placeholderChange" />
    <Evaluation/>
  </div>
</template>

<script>
import Title from './components/Title.vue'
import TodoInput from './components/TodoInput.vue'
import Option from './components/Option.vue'
import Evaluation from './components/Evaluation.vue'

export default {
  components: {
    Title,
    TodoInput,
    Option,
    Evaluation
  },
  methods: {
    // モード切り替えメソッド
    placeholderChange() {
      console.log("成功")
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
