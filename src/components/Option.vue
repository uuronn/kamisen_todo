<template>
  <div class="option">
    <h3>{{ mode }}モード</h3>
    <div class="option_top">
      <div class="option_top_button" @click="openOption" >
        <img class="option_top_button-img" src="../assets/option_button-img.png" alt="ハンバーガーメニュー画像">
      </div>
      <div class="option_top_content" v-if="optionIsShow">
        <div class="content_mode">
          <button @click="switchButton">切り替え</button>
          <button v-if="buttonMenu" @click="defaultMode">デフォルトモード</button>
          <button v-if="buttonMenu" @click="dissMode">煽りモード</button>
          <button v-if="buttonMenu" @click="muscleMode">筋トレモード</button>
        </div>
        <div class="content_x">
          <button>aaaa</button>
          <button>ddddd</button>
          <button>fdfdfd</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "option",
  data() {
    return {
      mode: 'デフォルト',
      buttonMenu: false,
      optionIsShow: false
    }
  },
  methods: {
    // モードを切り替えるボタンを表示させるメソッド
    switchButton() {
        this.buttonMenu = !this.buttonMenu
    },
    // デフォルトモードにするメソッド
    defaultMode() {
      this.mode = "デフォルト"
      this.buttonMenu = false
    },
    // 煽りモードにするメソッド
    dissMode() {
      this.mode = "煽り"
      this.buttonMenu = false
    },
    // 筋トレモードにするメソッド
    muscleMode() {
      this.mode = "筋トレ"
      this.buttonMenu = false
    },
    openOption() {
      this.optionIsShow = !this.optionIsShow
    }
  }
}
</script>

<style scoped>
  /* .option {
    display: flex;
    position: absolute;
    right: 4%;
  }

  .option_top {
    display: flex;
    flex-flow: column;
    text-align: center;
    margin-right: 0;
    width: 300px;
  }

  .option_top_button {
    width: 50px;
  }

  .option_top_button-img {
    
    width: 50px;
    transition: 1s;
  }

  .option_top_button-img:hover {
    border-radius: 20px;
    transition: 1s;
  }

  .option_top_content {
    display: flex;
    text-align: right;
  }

  .content_mode {
    display: flex;
    flex-flow: column;
    min-width: 130px;
  }

  .content_x {
    text-align: right;
  } */
</style>
