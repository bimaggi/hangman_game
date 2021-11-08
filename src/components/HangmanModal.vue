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
  },
}
</script>

<style lang="stylus">
.modal__backdrop
  position absolute
  z-index 9999
  top 0
  bottom 0
  left 0
  right 0
  background-color rgba(#fff, .8 )
  display flex
  flex-direction column
  justify-content center
  align-items center

.modal__message
  background-color green

.modal__button
  cursor pointer

.modal--fade-enter, .modal--fade--leave-active
  opacity 0
  top -10px
.modal--fade-enter-active, .modal--fade-leave-active
  transition all .4s ease
</style>
