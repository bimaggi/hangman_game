<template>
    <footer class="footer">
    <p>
        <a href="https://www.linkedin.com/in/marcia-b-oliveira/"
          class="footer__link"
          target="_blank">
        <strong>
          Marcia Bimaggi - 2021 - Projeto desenvolvido em Vue.js
        </strong>
      </a>
    </p>
</footer>
</template>
<script>
export default {
  name: 'AppFooter',
}
</script>
<style lang="stylus" scoped>
 .footer
  text-align: center
  margin-top 1%
  font-size 16px
  font-family 'sans-serif'
  @media screen and (max-width $mobile)
    font-size 12px
    width: 100%
    padding 2%

.footer__link
  letter-spacing: 1px
  text-decoration: none
  color $text
</style>
