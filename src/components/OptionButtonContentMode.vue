<template>
  <div class="optionContent__item">
    <button class="optionContent__button" @click="hundleClick">モード切り替え</button>
    <button class="optionContent__button" v-if="modeShow" @click="defaultMode">デフォルトモード</button>
    <button class="optionContent__button" v-if="modeShow" @click="dissMode">煽りモード</button>
    <button class="optionContent__button" v-if="modeShow" @click="muscleMode">筋トレモード</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      modeShow: false,
    }
  },
  methods: {

    // ボタンを表示させるメソッド
    hundleClick() {
      this.modeShow = !this.modeShow
    },
    defaultMode() {
      this.$emit("defaultMode")
    },
    dissMode() {
      this.$emit("dissMode")
    },
    muscleMode() {
      this.$emit("muscleMode")
    },
  }
}
</script>
