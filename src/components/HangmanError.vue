<template>
  <div class="error">
    <img
      :src="`https://raw.githubusercontent.com/william-costa/wdev-hangman-game-resources/master/images/hangman/${error}.svg`"
      class="error__image"
      >
  </div>
</template>

<script>
export default {
  name: 'HangmanError',
  props: {
    error: Number,
  },
}
</script>

<style lang="stylus" scoped>
.error__image
  width 200px
</style>
