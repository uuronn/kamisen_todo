<template>
  <div>
    <button class="optionContent__button" @click="switchAction">切り替え</button>
        <button class="optionContent__button" v-if="modeShow" @click="defaultMode">デフォルトモード</button>
        <button class="optionContent__button" v-if="modeShow" @click="dissMode">煽りモード</button>
        <button class="optionContent__button" v-if="modeShow" @click="muscleMode">筋トレモード</button>
  </div>
</template>