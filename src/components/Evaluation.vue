<template>
  <div>
    <button>評価</button>
  </div>
</template>

<style lang="scss" scoped>
  div {
    display: flex;
    justify-content: center;
    align-items: center;
    position: absolute;
    right: -2vw;
    bottom: -4vh;
    width: 50vh;
    height: 50vh;
    overflow: hidden;
      button {
        width: 30%;
        height: 30%;
        background: #fff;
        border-radius: 200px;
        transition: 1s;
      }
      button:hover {
        width: 60%;
        height: 60%;
        transition: 1s;
      }
  }

</style>