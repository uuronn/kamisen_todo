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
    right: -6vw;
    bottom: -12vh;
    width: 30vw;
    height: 30vw;
    pointer-events: none;
    div:hover {
      z-index: 2;
    }
    button {
      width: 30%;
      height: 30%;
      border-radius: 50%;
      transition: 0.5s;
      font-size: 40px;
      border: 1px solid #CC1669;
      pointer-events: auto;
      background-color: #fff;
      animation-duration: 1s;
    }
    // button:hover {
    //   border: 240px solid;
    //   width: 100%;
    //   height: 100%;
    //   transition: 0.5s;
    // }
    button:hover {
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
  // div {
  //   width: 50vh;
  //   height: 50vh;
  //     button {
  //       width: 30%;
  //       height: 30%;
  //       background: #fff;
  //       border-radius: 200px;
  //       transition: 1s;
  //     }
  //     button:hover {
  //       width: 60%;
  //       height: 60%;
  //       transition: 1s;
  //     }
  // }

</style>