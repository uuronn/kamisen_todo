<template>
  <div class="evaluation">
    <button
      class="evaluation__button"
      @click="hundleClick"
    >
      {{ btnName }}
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      btnName: "評価"
    }
  },
  methods: {
    hundleClick() {
      confirm("あなたのランクは～です")
    }
  }
}
</script>

<style lang="scss" scoped>
.evaluation {
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  z-index: 10;
  right: 0.5vw;
  bottom: 0.5vw;

  &__button {
    width: 100px;
    height: 50px;
    border-radius: 10px;
    border: 1px solid #000;
    background: #fff;
    font-weight: bold;

    &:hover {
      background: $button-hover;
    }
  }
}
</style>
