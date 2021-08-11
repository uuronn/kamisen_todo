<template>
  <div class="optionContent__item">
    <button class="optionContent__button" @click="hundleClick">時間切れしたタスク</button>
    <button class="optionContent__button" v-if="sampleShow">中身</button>
    <button class="optionContent__button" v-if="sampleShow">中身</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      sampleShow: false
    }
  },
  methods: {
    hundleClick() {
      this.sampleShow = !this.sampleShow
    }
  }
}
</script>
