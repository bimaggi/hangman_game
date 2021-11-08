<template>
  <div class="board">
    <button
      class="board__button"
      v-for="(letter,key) in 'abcdefghijklmnopqrstuvwxyz'"
      :key="key"
      :disabled="validateLetter(letter)"
      @click="setPlay(letter)"
    >
      {{letter}}
    </button>
  </div>
</template>

<script>
export default {
  name: 'HangmanBoard',
  props: {
    letters: Array,
    validateLetter: Function,
    setPlay: Function,
  },
}
</script>
<style lang="stylus" scoped>
.board__button
  width 35px
  height @width
  flex-wrap wrap
  margin 5px
  border-radius 5px
  cursor pointer
  text-transform uppercase

</style>
