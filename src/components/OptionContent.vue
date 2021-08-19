<template>
  <div class="optionContent">
    <ul class="optionContent__list">
      <OptionContentItem :options="modes" @onClick="onClick" title="モード切り替え" />
      <OptionContentItem :options="completed" title="完了したタスク" />
      <OptionContentItem :options="timeout" title="時間切れしたタスク" />
      <OptionContentItem :options="sample" title="テストするボタン" />
    </ul>
  </div>
</template>

<script>
import OptionContentItem from "./OptionContentItem.vue";

export default {
  props: ['modes'],
  data() {
    return {
      sample: [
        {
          click() {
            console.log("成功")
          },
          btnName: "テストボタン中身"
        }
      ],
      completed: [
        {
          click: () => null,
          btnName: "中身"
        },
        {
          click: () => null,
          btnName: "中身"
        }
      ],
      timeout: [
        {
          click: () => null,
          btnName: "中身"
        },
        {
          click: () => null,
          btnName: "中身"
        }
      ]
    };
  },
  components: {
    OptionContentItem
  },
  methods: {
    // モードを切り替えるボタンを表示させるメソッド
    switchAction() {
      this.modeShow = !this.modeShow;
    },

    onClick(option) {
      this.$emit('onClick', option)
      this.$emit("placeChange", option)
    },

    // デフォルトモードにするメソッド
    defaultMode() {
      this.$emit("defaultMode");
      // this.buttonMenu = false
      // this.$emit("clickModes"," taskName")
    },

    // 煽りモードにするメソッド
    dissMode() {
      this.$emit("dissMode");
      // this.buttonMenu = false
      // this.$emit("clickModes"," はよ仕事しろ")
    },

    // 筋トレモードにするメソッド
    muscleMode() {
      this.$emit("muscleMode");
      // this.mode = "筋トレ"
      // this.buttonMenu = false
      // this.$emit("clickModes"," 腹筋バキバキ！")
    },

    // sample
    sampleAction() {
      this.sampleShow = !this.sampleShow;
    }
  }
};
</script>

<style lang="scss" scoped>
.optionContent {
  &__list {
    display: flex;
  }
}
</style>
