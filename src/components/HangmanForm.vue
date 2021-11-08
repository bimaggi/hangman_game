<template>
<div>
  <div
    v-if="stageInitial === 'word'"
  >
    <label for="">
      {{steps.setWord.title}}
    </label>
    <input
      type="text"
      v-model="word"
    >
    <button
     @click="setWord"
    >
      {{steps.setWord.button}}
    </button>
  </div>
  <div
    v-if="stageInitial === 'tip'"
  >
    <label
      for="">
      {{steps.setTip.title}}
    </label>
    <input
      type="text"
      v-model="tip"
    >
    <button
      @click="setTip"
    >
      {{steps.setTip.button}}
    </button>
  </div>
</div>
</template>

<script>
export default {
  name: 'HangmanForm',
  data() {
    return {
      stageInitial: 'word',
      tip: null,
      word: null,
      actualWord: null,
      actuakTip: null,
      steps: {
        setWord: {
          title: 'Defina a palavra',
          button: 'Próximo',
        },
        setTip: {
          title: 'Defina a dica',
          button: 'Jogar',
        },
      },
    }
  },
  methods: {
    setWord() {
      this.actualWord = this.word
      this.$emit('setWord', this.actualWord)
      this.stageInitial = 'tip'
    },
    setTip() {
      this.actualTip = this.tip
      this.$emit('setTip', this.actualTip)
    },

  },
}
</script>
