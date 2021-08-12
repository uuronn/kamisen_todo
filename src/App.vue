<template>
  <div class="root">
    <TheTitle />
    <TodoInput />
    <OptionButton @clickModes="changeModes" />
    <TheEvaluation />
  </div>
</template>

<script>
import TheTitle from "./components/Title.vue";
import TodoInput from "./components/TodoInput.vue";
import OptionButton from "./components/Option.vue";
import TheEvaluation from "./components/Evaluation.vue";

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
      this.placeholder = index;
    }
  }
};
</script>

<style lang="scss" scoped>
.root {
  min-height: 100vh;
  position: relative;
  overflow: hidden;
  background: #cc1669;
}
</style>
