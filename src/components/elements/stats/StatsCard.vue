<template>
  <div class="Stats-Card flex flex-col items-center text-black text-center bg-white mx-2 my-2 lg:my-0 p-16 shadow-lg">
    <img class="h-16 mb-8" :src="content.imgSrc" :alt="content.title">
    <h2 class="text-lg font-light mb-2">{{ content.title }}</h2>
    <p class="text-sm font-bold" v-html="content.description" />
  </div>
</template>

<script>
import GeneralMixin from '../../../mixins/GeneralMixin'

export default {
  mixins: [GeneralMixin]
}
</script>

<style>
  .Stats-Card {
    min-width: 266px;
    width: 266px;
    min-height: 300px;
    max-height: 300px;
  }
</style>