<template>
  <div class="option">
    <h3 class="option__announce">{{ mode }}モード</h3>
    <div class="option__container">
      <div class="option__button" @click="openOption" >
        <img
          class="option__image"
          src="../assets/option_button-img.png"
          alt="ハンバーガーメニュー画像"
        />
      </div>
      <div class="option__content" v-if="optionIsShow">
        <div class="option__mode">
          <button class="option__switch" @click="switchButton">切り替え</button>
          <button class="option__default" v-if="buttonMenu" @click="defaultMode">デフォルトモード</button>
          <button class="option__diss" v-if="buttonMenu" @click="dissMode">煽りモード</button>
          <button class="option__muscle" v-if="buttonMenu" @click="muscleMode">筋トレモード</button>
        </div>
        <div class="option__x">
          <button @click="aaa">aaaaa</button>
          <button v-if="ok">bbbbbbbbb</button>
          <button v-if="ok">cccccccccccccc</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "option",
  data() {
    return {
      mode: 'デフォルト',
      optionIsShow: false,
      buttonMenu: false,
      ok: false
    }
  },
  methods: {
    // モードを切り替えるボタンを表示させるメソッド
    switchButton() {
        this.buttonMenu = !this.buttonMenu
    },
    // デフォルトモードにするメソッド
    defaultMode() {
      this.mode = "デフォルト"
      this.buttonMenu = false
    },
    // 煽りモードにするメソッド
    dissMode() {
      this.mode = "煽り"
      this.buttonMenu = false
    },
    // 筋トレモードにするメソッド
    muscleMode() {
      this.mode = "筋トレ"
      this.buttonMenu = false
    },
    openOption() {
      this.optionIsShow = !this.optionIsShow
    },
    aaa() {
      this.ok = !this.ok
    }
  }
}
</script>

<style lang="scss" scoped>
  // .option {
  //   position: absolute;
  //   width: 30vw;
  //   top: 0;
  //   right: 0;
  //   .option_top {
  //     .option_top_button {
  //       width: 5vw;
  //       margin-left: auto;
  //       .option_top_button-img {
  //         width: 100%;
  //       }
  //     }
  //     .option_top_content {
  //       display: inline;
  //     }
  //   }
  // }
  
</style>
