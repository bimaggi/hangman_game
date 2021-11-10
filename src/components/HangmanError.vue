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
  adjustments()
  @media screen and (max-width $mobile)
    margin-top 0
    margin-bottom 0

.error__image
  width 200px
  text-align center
  @media screen and (max-width $mobile)
    width 180px
</style>
