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
        <div class="option__sample">
          <button class="option__btn" @click="sampleAction">ボタン</button>
          <button class="option__show" v-if="sampleShow">中身</button>
          <button class="option__show" v-if="sampleShow">中身</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mode: 'デフォルト',
      optionIsShow: false,
      buttonMenu: false,
      sampleShow: false
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
    
    // ハンバーガーメニューの中身を表示させるメソッド
    openOption() {
      this.optionIsShow = !this.optionIsShow
    },

    // test
    sampleAction() {
      this.sampleShow = !this.sampleShow
    }
  }
}
</script>

<style lang="scss" scoped>


.option {
  position: absolute;
  z-index: 1;
  right: 0;
  top: 0;

  &__button {
    width: 50px;
    margin-left: auto;
  }

  &__image {
      width: 100%;
      border-radius: 10px;
  }
  
  &__content {}

  &__mode,&__sample {}

  &__btn {
    background: #fff;
  }
}
</style>
