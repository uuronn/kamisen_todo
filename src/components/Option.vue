<template>
  <div class="option">
    <span class="option__announce">{{ mode }}モード</span>
    <button class="option__button" @click="openOption">
      <span class="option__style"></span>
      <span class="option__style"></span>
      <span class="option__style"></span>
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
      sampleShow: false,
    }
  },
  components: {
    OptionList
  },
  methods: {
    // ハンバーガーメニューの中身を表示させるメソッド
    openOption() {
      this.optionIsShow = !this.optionIsShow
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
    flex-direction: column;
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
}
</style>
