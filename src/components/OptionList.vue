<template>
  <div class="optionList">
    <div class="optionList__container">
      <button class="optionList__button" @click="switchButton">切り替え</button>
      <button class="optionList__button" v-if="buttonMenu" @click="defaultMode">デフォルトモード</button>
      <button class="optionList__button" v-if="buttonMenu" @click="dissMode">煽りモード</button>
      <button class="optionList__button" v-if="buttonMenu" @click="muscleMode">筋トレモード</button>
    </div>
    <div class="optionList__container--sample">
      <button class="optionList__button" @click="sampleAction">サンプルボタン</button>
      <button class="optionList__button" v-if="sampleShow">中身</button>
      <button class="optionList__button" v-if="sampleShow">中身</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      buttonMenu: false,
      sampleShow: false,
    }
  },
  methods: {
    // モードを切り替えるボタンを表示させるメソッド
    switchButton() {
      this.buttonMenu = !this.buttonMenu
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

<style lang="scss" scoped>
.optionList {
  display: flex;

  // 切り替えボタン
  &__container {
    display: flex;
    flex-flow: column;
    min-width: 152px;
  }

  // サンプルボタン
  &__container--sample {
    display: flex;
    flex-flow: column;
  }

  // すべてのボタン
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
