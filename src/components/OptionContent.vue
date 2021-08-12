<template>
  <div class="optionContent">
    <ul class="optionContent__list">
      <OptionContentItem :data="mode" title="モード切り替え" />
      <OptionContentItem :data="completed" title="完了したタスク" />
      <OptionContentItem :data="timeout" title="時間切れしたタスク" />
    </ul>
  </div>
</template>

<script>
import OptionContentItem from "./OptionContentItem.vue";

export default {
  data() {
    return {
      sampleShow: false,
      mode: [
        {
          click: this.defaultMode,
          title: "デフォルトモード"
        },
        {
          click: this.dissMode,
          title: "煽りモード"
        },
        {
          click: this.muscleMode,
          title: "筋トレモード"
        }
      ],
      completed: [
        {
          click: () => null,
          title: "中身"
        },
        {
          click: () => null,
          title: "中身"
        }
      ],
      timeout: [
        {
          click: () => null,
          title: "中身"
        },
        {
          click: () => null,
          title: "中身"
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
