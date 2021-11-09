<template>
  <div class="error">
    <img
      :src="require(`@/assets/${error}.png`)"
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
.error
  display flex
  align-items center
  justify-content center

.error__image
  width 200px
  text-align center
</style>
