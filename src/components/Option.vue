<template>
  <div class="option">
    <span class="option__announce">{{ mode }}モード</span>
    <button class="option__button" @click="openOption">
      <span class="option__style" :class="topLine"></span>
      <span class="option__style" :class="centerLine"></span>
      <span class="option__style" :class="bottomLine"></span>
    </button>
    <OptionList v-if="optionIsShow"/>
  </div>
</template>

<script>
import OptionList from './OptionList.vue'

export default {
  data() {
    return {
      mode: 'デフォルト',
      optionIsShow: false,
      topLineStyle: false,
      centerLineStyle: false,
      bottomLineStyle: false
    }
  },
  components: {
    OptionList
  },
  methods: {
    // ハンバーガーメニューの中身を表示させるメソッド
    openOption() {
      this.optionIsShow = !this.optionIsShow
      this.topLineStyle = !this.topLineStyle
      this.centerLineStyle = !this.centerLineStyle
      this.bottomLineStyle = !this.bottomLineStyle
    }
  },
  computed: {
    topLine() {
      return {
        option__topLine: this.topLineStyle
      }
    },
    centerLine() {
      return {
        option__centerLine: this.centerLineStyle
      }
    },
    bottomLine() {
      return {
        option__bottomLine: this.bottomLineStyle
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.option {
  position: absolute;
  z-index: 10;
  right: 0.5vw;
  top: 0.5vw;
  text-align: right;

  // ハンバーガーボタン
  &__button {
    display: flex;
    justify-content: center;
    flex-flow: column;
    background: #fff;
    width: 56px;
    height: 56px;
    margin-left: auto;
    border: 1px solid #000;
    border-radius: 8px;
  }

  // ハンバーガーボタンの三本線
  &__style {
    margin: 4px auto;
    width: 80%;
    height: 6px;
    border-radius: 50px;
    background: #000;
  }

  // 三本線の一番上
  &__topLine {
    animation-name: topAnimation;
    animation-fill-mode: forwards;
    animation-duration: 1s;
    margin-left: 11px;
    
    @keyframes topAnimation {
      100% {
        transform-origin: left;
        transform: rotate(-319deg);
      }
    }
  }

  // 三本線の真ん中
  &__centerLine {
    background: #fff;
    transition: 1s;
  }

  // 三本線の一番下
  &__bottomLine {
    animation-name: bottomAnimation;
    animation-fill-mode: forwards;
    animation-duration: 1s;
    margin-left: 11px;
    
    @keyframes bottomAnimation {
      100% {
        transform-origin: left;
        transform: rotate(319deg);
      }
    }
  }
}
</style>
