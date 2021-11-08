<template>
  <div class="hangman">
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
      v-if=" stage === 'play'"
    >
      <hangman-play
        :isWord="isWord"
        :isTip="isTip"
        :error="error"
        :validateLetter="validateLetter"
        :letters="letters"
      />
    </section>
  </div>
</template>
<script>
import AppHeader from '@/components/AppHeader'
import HangmanForm from '@/components/HangmanForm'
import HangmanPlay from '@/components/HangmanPlay'

export default {
  name: 'HangmanGame',
  components: {
    AppHeader,
    HangmanForm,
    HangmanPlay,

  },
  data() {
    return {
      stage: 'init',
      isWord: null,
      isTip: null,
      error: 0,
      letters: [],
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
    validateLetter(value) {
      return value === 'a'
    },
  },
}
</script>
