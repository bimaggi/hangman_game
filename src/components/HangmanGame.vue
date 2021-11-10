<template>
  <div class="hangman">
    <hangman-modal
      v-if="finalMessage"
      :finalMessage="finalMessage"
      :restart="restart"
      :isWord="isWord"
      />
    <app-header/>
    <section
      v-if=" stage === 'init'"
    >
      <hangman-form
        @setWord="setWord"
        @setTip="setTip"
      />
    </section>
    <section
      v-if="stage === 'play'"
    >
      <hangman-play
        :isWord="isWord"
        :isTip="isTip"
        :error="error"
        :validateLetter="validateLetter"
        :letters="letters"
        :stage="stage"
        :setPlay="setPlay"
        :finalMessage="finalMessage"
      />
    </section>
  </div>
</template>
<script>
import AppHeader from '@/components/AppHeader'
import HangmanForm from '@/components/HangmanForm'
import HangmanPlay from '@/components/HangmanPlay'
import HangmanModal from '@/components/HangmanModal'

export default {
  name: 'HangmanGame',
  components: {
    AppHeader,
    HangmanForm,
    HangmanPlay,
    HangmanModal,
  },
  data() {
    return {
      stage: 'init',
      isWord: null,
      isTip: null,
      error: 0,
      letters: [],
      finalMessage: null,
    }
  },
  methods: {
    setWord(value) {
      this.isWord = value
    },
    setTip(value) {
      this.isTip = value
      this.stage = 'play'
    },
    validateLetter(letter) {
      return this.letters.find((item) => item.toLowerCase() === letter.toLowerCase())
    },
    setPlay(letter) {
      // adiciona no array a letra que foi jogada
      this.letters.push(letter)

      // validar o erro
      this.validateError(letter)
    },
    validateError(letter) {
      // acertos
      if (this.isWord.toLowerCase().indexOf(letter.toLowerCase()) >= 0) {
        return this.validateWinner()
      }
      // erros
      this.error += 1
      // enforcado
      if (this.error === 6) {
        this.finalMessage = 'Que pena, você foi enforcado!'
      }
    },
    validateWinner() {
      // dessa forma não vai contabilizar letras iguais, mais de uma vez
      const uniqueLetter = [...new Set(this.isWord.split(''))]
      if (uniqueLetter.length === (this.letters.length - this.error)) {
      // this.stage = 'winner'
        this.finalMessage = 'Parabéns, você se livrou de ser enforcado!'
      }
    },
    restart() {
      window.location.reload()
    },
  },
}
</script>

<style lang="stylus">
.hangman
  adjustments()
  flex-direction column
</style>
