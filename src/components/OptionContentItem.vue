<template>
  <div class="optionContentItem">
    <button class="optionContentItem__button" @click="showContent">
      {{ title }}
    </button>
    <div class="optionContentItem__wrapper" v-if="modeShow">
      <button
        class="optionContentItem__button"
        v-for="(option, i) in options"
        :key="i"
        @click="onClick(option)"
      >
        {{ option.mode }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["options", "title"],
  data() {
    return {
      modeShow: false,
    }
  },
  methods: {
    // ボタンを表示させるメソッド
    showContent() {
      this.modeShow = !this.modeShow;
    },
    onClick(i) {
      this.$emit("onClick", i)
    }
  }
};
</script>

<style lang="scss" scoped>
.optionContentItem {
  display: flex;
  flex-direction: column;

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

  &__wrapper {
    display: flex;
    flex-direction: column;
  }
}
</style>
