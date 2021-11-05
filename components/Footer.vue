<template>
  <div class="footer">
    <div class="footer__wrapper">
      <div class="footer__left-side">
        <div class="footer__links">
          <a href="">О кооперативе</a>
          <a href="">Услуги</a>
          <a href="">Наши проекты</a>
          <a href="">Отзывы</a>
          <a href="">FAQ</a>
        </div>
        <a class="footer__policy" href="">Политика конфеденциальности</a>
      </div>
      <div class="footer__right-side">
        <div>+7 928 198 46 10</div>
        <div>kooperativ@mail.ru</div>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  
})
</script>
<style lang="stylus" scoped>
.footer
  background #000
  &__wrapper
    padding 80px 0
    max-width 1190px
    margin 0 auto
    color black
    display flex
    justify-content space-between
    color white
    a
      text-decoration none
  &__links
    padding-bottom 37px
    font-size 20px
    line-height 1.5
    text-decoration none
    a
      color white
      &:not(:last-child)
        padding-right 40px
  &__policy
    font-size 15px
    line-height 1.5
    color white 
    opacity 0.5
    text-decoration none
  &__right-side
    font-size 20px
    div
      &:first-child
        padding-bottom 37px
</style>