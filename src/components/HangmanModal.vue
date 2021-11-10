<template>
<transition name="modal--fade">
  <div
    class="modal__backdrop"
  >
    <h1
      class="modal__message"
    >
      {{finalMessage}}
    </h1>
    <h2
      class="modal__word">
        Palavra secreta: " {{isWord}} "
      </h2>
    <button
      class="modal__button"
      @click="restart"
    >
      Jogar novamente
    </button>
  </div>
</transition>
</template>

<script>
export default {
  name: 'HangmanModal',
  props: {
    finalMessage: String,
    restart: Function,
    isWord: String,
  },
}
</script>

<style lang="stylus" scoped>
.modal__backdrop
  position absolute
  z-index 9999
  top 0
  bottom 0
  left 0
  right 0
  adjustments()
  background()
  flex-direction column
  @media screen and (max-width $mobile)
    font-size 18px
    height 100%
    top 4%
    left 4%
    right 4%
    border-radius $radius

.modal__message
  width 100%
  text-align center
  margin-top 1%
  letter-spacing $spacing
  font-weight 5
  @media screen and (max-width $mobile)
    width 90%
    margin-top 0

.modal__word
  text-transform uppercase
  letter-spacing $spacing
  margin-top 5%
  font-weight lighter
  @media screen and (max-width $mobile)
    width 90%
    font-size: 22px
    margin-top 10%
    text-align center
    flex-wrap wrap

.modal__button
  margin-top: 2%
  cursor pointer
  border 2px solid black
  border-radius $radius
  letter-spacing 4px
  background-color transparent
  @media screen and (max-width $mobile)
    margin-top 20%
    font-size 25px




</style>
