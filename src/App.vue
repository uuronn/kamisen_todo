<template>
  <div class="root">
    <Title/>
    <TodoInput :modes="modes" @placetest="placetest" />
    <Option
      @placeChange="placeChange"
      :modes="modes"
    />
    <Evaluation/>
  </div>
</template>

<script>
import Title from './components/Title.vue'
import TodoInput from './components/TodoInput.vue'
import Option from './components/Option.vue'
import Evaluation from './components/Evaluation.vue'




export default {
  data() {
    return {
      modes: [
        {
          mode: 'デフォルトモード',
          placeholder: ' taskName'
        },
        {
          mode: '煽りモード',
          placeholder: ' はよ仕事しろ'
        },
        {
          mode: '筋トレモード',
          placeholder: ' 腹筋バキバキ！'
        }
      ],
    }
  },
  components: {
    Title,
    TodoInput,
    Option,
    Evaluation
  },
  methods: {
    // モード切り替えメソッド
    placeChange() {
      this.$emit('placetest')
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
