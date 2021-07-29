<template>
  <div class="evaluation">
    <div class="evaluation__container">
      <button class="evaluation__button">
        評価
      </button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.evaluation {
  
  &__container {
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    right: -4vw;
    bottom: -4vw;
    width: 25vw;
    height: 25vw;
    min-width: 120px;
    min-height: 120px;
  }

  &__button {
    width: 50%;
    height: 50%;
    border-radius: 50%;
    font-size: 4vw;
    border: 2px solid;
    background-color: $button-back;

    &:hover {
      background: $button-hover;
      animation-name: evaluation;
      animation-duration: 1s;

      @keyframes evaluation {
        0% {
          width: 50%;
          height: 50%;
        }

        50% {
          width: 100%;
          height: 100%;
          font-size: 8vw;
        }
      }
    }
  }
}
</style>
