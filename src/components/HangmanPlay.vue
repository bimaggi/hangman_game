<template>
  <div class="word">
    <hangman-error
      :error="error"
    />
    <div class="play__words">
      <div
        class="play__word"
        v-for="(letter,key) in isWord" :key="key"
      >
        {{(validateLetter(letter) || finalMessage) ? letter : ''}}
        <!--{{(validateLetter(letter) || stage === 'hanged') ? letter : ''}}-->
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
        :setPlay="setPlay"
        :error="error"
      />
    </div>
  </div>
</template>

<script>
import HangmanBoard from '@/components/HangmanBoard'
import HangmanError from '@/components/HangmanError'

export default {
  name: 'HangmanPlay',
  props: {
    isWord: String,
    isTip: String,
    error: Number,
    validateLetter: Function,
    letters: Array,
    stage: String,
    setPlay: Function,
    finalMessage: String,
  },
  components: {
    HangmanBoard,
    HangmanError,
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

.play__tip
  text-align center
  margin-top 20px
  letter-spacing 8px
</style>
