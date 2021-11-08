<template>
  <div class="board">
    <button
      class="board__button"
      v-for="(letter,key) in 'abcdefghijklmnopqrstuvwxyz'"
      :key="key"
      :disable="validateLetter(letter)"
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
    validateLetter: String,
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

</style>
