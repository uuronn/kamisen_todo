<template>
  <div class="optionContentItem">
    <button class="optionContentItem_button" @click="hundleClick">
      {{ title }}
    </button>
    <div v-if="modeShow">
      <button
        v-for="(btn, i) in data"
        :key="i"
        class="optionContentItem__button"
        @click="btn.click"
      >
        {{ btn.title }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["data", "title"],
  data() {
    return {
      modeShow: false
    };
  },
  methods: {
    // ボタンを表示させるメソッド
    hundleClick() {
      this.modeShow = !this.modeShow;
    },
    defaultMode() {
      this.$emit("defaultMode");
    },
    dissMode() {
      this.$emit("dissMode");
    },
    muscleMode() {
      this.$emit("muscleMode");
    }
  }
};
</script>

<style lang="scss" scoped>
.optionContentItem {
  display: flex;
  flex-direction: column;

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
