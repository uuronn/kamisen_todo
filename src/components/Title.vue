<template>
  <div class="title">
    <h1 class="title__font">神の宣告</h1>
  </div>
</template>

<style lang="scss" scoped>
.title {
  margin: 5vw auto 3vw auto;
  text-align: center;
  
  &__font {
    font-size: 5vw;
  }

  @media screen and (max-width: 720px) {
    width: 10vw;
    &__font {
      font-size: 40px;
    }
  }
}
</style>
