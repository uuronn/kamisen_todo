<template>
  <div class="evaluation">
    <button class="evaluation__button">評価</button>
  </div>
</template>

<style lang="scss" scoped>
  .evaluation {
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    right: -6vw;
    bottom: -12vh;
    width: 30vw;
    height: 30vw;
    &:hover {
      z-index: 2;
    }
    &__button {
      width: 30%;
      height: 30%;
      border-radius: 50%;
      font-size: 40px;
      border: 1px solid #CC1669;
      pointer-events: auto;
      font-size: 4vw;
      font-family: 'HG正楷書体-PRO';
      background-color: #fff;
      animation-duration: 1s;
    }
    &__button:hover {
      animation-name: test1;
      animation-duration: 1s;
    }
    @keyframes test1 {
      0% {
        width: 30%;
        height: 30%;
      }
      50% {
        width: 100%;
        height: 100%;
        font-size: 100px;
      }
    }
  }
</style>
