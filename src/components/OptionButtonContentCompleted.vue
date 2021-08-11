<template>
    <div class="OptionContent">
        <button class="optionList__button" @click="CompletedAction">完了したタスク</button>
        <!-- had comps -->
        <button class="optionList__button" v-if="sampleShow">中身</button>
        <button class="optionList__button" v-if="sampleShow">中身</button>
      </div>
</template>