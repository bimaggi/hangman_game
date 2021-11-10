<template>
<div class="form">
  <div
    class="form__word"
    v-if="stageInitial === 'word'"
  >
    <label
      class="word__title"
      for="word"
    >
      {{steps.setWord.title}}
    </label>
    <input
      class="input"
      type="text"
      v-model="word"
    >
    <button
    class="button"
     @click="setWord"
    >
      {{steps.setWord.button}}
    </button>
  </div>
  <div
    class="form__tip"
    v-if="stageInitial === 'tip'"
  >
    <label
      class="tip__title"
      for="tip">
      {{steps.setTip.title}}
    </label>
    <input
      class="input"
      type="text"
      v-model="tip"
    >
    <button
      class="button"
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
<style lang="stylus" scoped>
.form
  margin-top 35%
  text-align center
  letter-spacing 8px

.form__word
  display flex
  flex-direction column
  align-items center

.form__tip
  @extends .form__word

.word__title
  margin-bottom: 2%
  @media screen and (max-width $mobile)
    font-size 25px

.input
  margin-bottom 20px
  border-radius $radius
  width 100%
  letter-spacing $spacing
  border $border
  background-color transparent
  @media screen and (max-width $mobile)
    width 90%
    margin-top: 3%

.button
  width 60%
  letter-spacing $spacing
  background-color transparent
  border $border
  border-radius $radius
  cursor pointer
  @media screen and (max-width $mobile)
    width 50%
    font-size 25px
    padding: 1%
    margin-top 3%

</style>
