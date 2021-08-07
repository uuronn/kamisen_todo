<template>
  <div class="option">
    <span class="option__announce">{{ mode }}モード</span>
    <div class="option__button" @click="openOption">
      <img
        class="option__image"
        src="../assets/option_button-img.png"
        alt="ハンバーガーメニュー画像"
      />
    </div>
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
      transform:rotate(180deg);
    }
  }
  
  &__content {
    display: flex;
    animation-name: test;
    animation-direction: 1s;
    transition: all 1s;
  }
}
</style>
