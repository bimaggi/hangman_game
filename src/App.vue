<template>
  <div id="app">
    <hangman-game/>
  </div>
</template>

<script>
import HangmanGame from '@/components/HangmanGame'

export default {
  name: 'App',
  components: {
    HangmanGame,
  },
}
</script>

<style lang="stylus">
 @import './styles/global.styl'
</style>
