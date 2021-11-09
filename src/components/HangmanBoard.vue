<template>
  <div class="board">
    <button
      class="board__button"
      v-for="(letter,key) in 'abcdefghijklmnopqrstuvwxyzãáéêíóõôú'"
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
.board
  width 80%
  display flex
  flex-wrap wrap
  margin auto
  margin-top 15px

 .board__button
  width 40px
  height @width
  margin 5px
  border-radius 5px
  cursor pointer
  text-transform uppercase
  background-color transparent
  border 2px solid black

</style>
