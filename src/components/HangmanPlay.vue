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
     <app-footer/>
  </div>
</template>

<script>
import HangmanBoard from '@/components/HangmanBoard'
import HangmanError from '@/components/HangmanError'
import AppFooter from '@/components/AppFooter'

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
    AppFooter,
  },
}
</script>

<style lang="stylus" scoped>
.word
  max-width 100%

.play__words
  text-transform uppercase
  adjustments()
  @media screen and (max-width $mobile)
    margin-top 0%
    flex-wrap wrap
    padding 0 5px 0 5px

.play__word
  adjustments()
  border-bottom 1px solid black
  margin 0px 5px
  width 30px
  height @width

.play__tip
  text-align center
  margin-top 20px
  letter-spacing $spacing
  @media screen and (max-width $mobile)
    adjustments()
    width 90%
    margin-top 5px
    margin-bottom 0

</style>
