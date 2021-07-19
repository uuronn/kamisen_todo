<template>
  <div class="evaluation">
    <div class="evaluation__container">
      <button class="evaluation__button">
        評価
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {

    }
  },
  methods: {
    
  }
}
</script>


<style lang="scss" scoped>
.evaluation {
  
  &__container {
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    right: -6vw;
    bottom: -6vw;
    width: 30vw;
    height: 30vw;
  }

  &__button {
    width: 50%;
    height: 50%;
    border-radius: 50%;
    font-size: 4vw;
    border: 2px solid;
    background-color: #fff;
    font-family: 'HG正楷書体-PRO';

    &:hover {
      background: #eee;
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
