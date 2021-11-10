<template>
  <div class="header">
    <h1 class="header__title">
        JOGO DA FORCA
    </h1>
  </div>
</template>

<script>
export default {
  name: 'AppHeader',
}
</script>

<style lang="stylus" scoped>
.header
  margin-top 6%

.header__title
  letter-spacing 10px
  @media screen and (max-width $mobile)
    letter-spacing $spacing
    width 100%
    font-size 35px
    margin-top 10%
</style>
