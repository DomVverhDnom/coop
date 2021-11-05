<template>
  <div class="services">
    <div class="services__wrapper">
      <div class="services-first">
        <span class="services__title">Услуги</span>
        <div class="services__icons">
          <img src="../assets/icons/circle-black.svg" alt="">
          <img src="../assets/icons/circle-start-white.svg" alt="">
        </div>
        <span class="services__title">Услуги</span>
      </div>
      <div class="services-second">
        <span class="services__title">Таргетированная реклама</span>
      </div>
      <div class="services-third">
        <span class="services__title">Web-разработка  &  упаковка продукта</span>
        <div class="services__icons">
          <img src="../assets/icons/hedgehog.svg" alt="">
          <img src="../assets/icons/point-black.svg" alt="">
          <img src="../assets/icons/circles.svg" alt="">
        </div>
      </div>
      <div class="services-four">
        <div class="services__icons">
          <img src="../assets/icons/circle-star-black.svg" alt="">
          <img src="../assets/icons/circle-hedgehog.svg" alt="">
        </div>
        <span class="services__title">Брендинг</span>
      </div>
      <div class="services-five">
        <span class="services__title">Все и сразу</span>
        <div class="services__icons">
          <img src="../assets/icons/circle-black.svg" alt="">
          <img src="../assets/icons/star-any.svg" alt="">
        </div>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    buttonContent: {
      type: Object,
      default: null,
    }
  }
})
</script>
<style lang="stylus" scoped>
  .services
    background #F3F3F3
    &-first
    &-second
    &-third
    &-four
    &-five
      margin-bottom 55px
    &-third
      color #FF4343
      &__icons
        display flex
        flex-direction column
    &__wrapper
      max-width 1200px
      margin 0 auto
      padding 100px 0
      text-transform uppercase
      *
        display flex
        justify-content space-between
    &__title
      font-size 100px
      line-height 0.9
    &__icons
      *:not(:first-child)
        margin-left 40px
</style>