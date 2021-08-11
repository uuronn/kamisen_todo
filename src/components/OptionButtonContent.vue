<template>
  <div class="optionContent">
    <ul class="optionContent__list">
      <OptionButtonContentMode/>
      <OptionButtonContentTimeout/>
      <OptionButtonContentCompleted/>
    </ul>
  </div>
</template>

<script>
import OptionButtonContentMode from './OptionButtonContentMode.vue'
import OptionButtonContentTimeout from './OptionButtonContentTimeout.vue'
import OptionButtonContentCompleted from './OptionButtonContentCompleted.vue'

export default {
  data() {
    return {
      sampleShow: false,
    }
  },
  components: {
    OptionButtonContentMode,
    OptionButtonContentTimeout,
    OptionButtonContentCompleted
  },
  methods: {
    // モードを切り替えるボタンを表示させるメソッド
    switchAction() {
      this.modeShow = !this.modeShow
    },
    
    // デフォルトモードにするメソッド
    defaultMode() {
      this.$emit("defaultMode")
      // this.buttonMenu = false
      // this.$emit("clickModes"," taskName")
    },

    // 煽りモードにするメソッド
    dissMode() {
      this.$emit("dissMode")
      // this.buttonMenu = false
      // this.$emit("clickModes"," はよ仕事しろ")
    },

    // 筋トレモードにするメソッド
    muscleMode() {
      this.$emit("muscleMode")
      // this.mode = "筋トレ"
      // this.buttonMenu = false
      // this.$emit("clickModes"," 腹筋バキバキ！")
    },

    // sample
    sampleAction() {
      this.sampleShow = !this.sampleShow
    }
  }
}
</script>

<style lang="scss">
// スコープなし
.optionContent {
  &__list {
    display: flex;
  }

  &__item {
    display: flex;
    flex-flow: column;
  }

  // 子コンポーネントのボタンスタイル
  &__button {
    min-width: 136px;
    border-radius: 4px;
    border: 2px solid;
    margin: 2px;
    background: $button-back;

    &:hover {
      background: $button-hover;
    }
  }
}
</style>
