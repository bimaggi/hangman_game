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
    restart: Function,
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
  background-color rgba(#FFFFE0, .8 )
  display flex
  flex-direction column
  align-items center

.modal__message
  width 100%
  text-align center
  margin-top 120px
  letter-spacing 5px

.modal__button
  margin-top: 16%
  cursor pointer
  border 2px solid black
  border-radius 5px
  letter-spacing 4px
  background-color rgba(#8B4513, .4)

.modal--fade-enter, .modal--fade--leave-active
  opacity 0
  top -10px
.modal--fade-enter-active, .modal--fade-leave-active
  transition all .4s ease
</style>
