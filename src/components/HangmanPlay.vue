<template>
  <div class="word">
    <div class="play__words">
      <div
        class="play__word"
        v-for="(letter,key) in isWord" :key="key"
      >
        {{validateLetter(letter) ? letter : ''}}
      </div>
    </div>
    <div
      class="play__tip"
    >
      Dica: {{isTip}}
    </div>
    <div>
      <hangman-board
       :letters="letters"
       :validateLetter="validateLetter"
      />
    </div>
  </div>
</template>

<script>
import HangmanBoard from '@/components/HangmanBoard'

export default {
  name: 'HangmanPlay',
  props: {
    isWord: String,
    isTip: String,
    error: Number,
    validateLetter: String,
    letters: Array,
  },
  components: {
    HangmanBoard,
  },
}
</script>

<style lang="stylus" scoped>
.play__words
  display flex
  text-transform uppercase
  text-align center
  justify-content center

.play__word
  display flex
  border-bottom 1px solid black
  margin 0px 5px
  width 30px
  height @width
  justify-content center
  align-items center

</style>
