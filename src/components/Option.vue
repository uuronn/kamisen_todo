<template>
  <div class="option">
    <h3 class="option__announce">{{ mode }}モード</h3>
      <div class="option__button" @click="openOption">
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
</template>

<script>
export default {
  props: {
  },
  data() {
    return {
      mode: 'デフォルト',
      optionIsShow: false,
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
      this.mode = "デフォルト"
      this.buttonMenu = false
      this.$emit("clickModes"," taskName")
    },

    // 煽りモードにするメソッド
    dissMode() {
      this.mode = "煽り"
      this.buttonMenu = false
      this.$emit("clickModes"," はよ仕事しろ")
    },

    // 筋トレモードにするメソッド
    muscleMode() {
      this.mode = "筋トレ"
      this.buttonMenu = false
      this.$emit("clickModes"," 終わらせないと筋トレだよ")
    },
    
    // ハンバーガーメニューの中身を表示させるメソッド
    openOption() {
      this.optionIsShow = !this.optionIsShow
    },

    // sample
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
  right: 0.5vw;
  top: 0.5vw;
  text-align: right;

  &__button {
    width: 50px;
    margin-left: auto;
  }

  &__image {
    width: 100%;
      border-radius: 8px;
      vertical-align:top;
      transition: 0.5s;

      &:hover {
        border-radius: 32px;
        transform:rotate(900deg);
      }
  }
  
  &__content {
    display: flex;
    animation-name: test;
    animation-direction: 1s;
    transition: all 1s;
  }

  &__mode {
    width: 144px;
    display: flex;
    flex-flow: column;
    transition: 1s;

    & button {
      border-radius: $button-radius;
      border: $button-border;
      margin: $mg-2;
      background: #fff;

      &:hover {
        background: $button-hover;
      }
    }
  }
  
  &__sample {
    // widthは確定ではない
    width: 80px;
    display: flex;
    flex-flow: column;
  }

  & button {
    background: #fff;
    border-radius: $button-radius;
    border: $button-border;
    margin: $mg-2;

    &:hover {
      background: $button-hover;
    }
  }
}
</style>
