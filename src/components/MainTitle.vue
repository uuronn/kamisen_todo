<template>
  <div class="MainTitle">
    <h1 class="MainTitle__font">神の宣告</h1>
  </div>
</template>

<style lang="scss" scoped>
.MainTitle {
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
