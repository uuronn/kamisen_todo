<template>
  <div class="optionContent">
    <ul class="optionContent__list">
      <div class="optionContent__item">
        <OptionButtonContentMode/>
      </div>
      <div class="optionContent__item">
        <OptionButtonContentCompleted/>
      </div>
      <div class="optionContent__item">
        <OptionButtonContentTimeout/>
      </div>
    </ul>
  </div>
</template>

<script>
import OptionButtonContentCompleted from './OptionButtonContentCompleted.vue'
import OptionButtonContentTimeout from './OptionButtonContentTimeout.vue'
import OptionButtonContentMode from './OptionButtonContentMode.vue'

export default {
  data() {
    return {
      modeShow: false,
      sampleShow: false,
    }
  },
  components: {
    OptionButtonContentCompleted,
    OptionButtonContentTimeout,
    OptionButtonContentMode
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
      // this.$emit("clickModes"," 腹筋6LDK目指しましょう")
    },

    // sample
    sampleAction() {
      this.sampleShow = !this.sampleShow
    }
  }
}
</script>

<style lang="scss">
.optionContent {
  display: flex;

  &__item {
    display: flex;
    flex-flow: column;
    min-width: 152px;
  }

  // すべてのボタンのスタイル
  &__button {
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
