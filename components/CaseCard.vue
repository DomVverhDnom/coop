<template>
  <div class="case">
    <div class="wrapper">
      <div class="left-side">
        <div class="left-side__wrapper">
          <div class="left-side__image-wrapper">
            <img  class="left-side__image" src="../assets/img/kimono.png" alt="">
          </div>
          <div class="left-side__name">Ателье-бутик Kimono Shop</div>
          <div class="left-side__service-type">SMM | Таргетированная реклама</div>
          <Button class="left-side__btn" :buttonContent="button"/>
        </div>
      </div>
        <div class="right-side">
          <div class="right-side__wrapper">
            <div class="right-side__number">3 400 588</div>
            <div class="right-side__text">охваченных пользователей</div>
          </div>
          <div class="right-side__wrapper">
            <div class="right-side__number">3 400 588</div>
            <div class="right-side__text">охваченных пользователей</div>
          </div>
          <div class="right-side__wrapper">
            <div class="right-side__number">3 400 588</div>
            <div class="right-side__text">охваченных пользователей</div>
          </div>
        </div>
      </div>
    </div>  
</template>
<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data() {
    return {
      button: {
        "color": "black",
        "text": "Подробнее", 
        "border": "none"
      }
    }
  }
})
</script>
<style lang="stylus" scoped>
// .case
  // width 80%
.wrapper
  display flex
  background #F3F3F3

  // justify-content space-between
.left-side
  &__wrapper
    position relative
    max-height 753px
  &__image
    max-width 640px
    height 100%
  &__name
    position absolute
    top 11%
    left 50%
    transform translateX(-50%)
    font-weight 500
    font-size 30px
    line-height 150%
    white-space nowrap
  &__service-type
    position absolute
    top 20%
    left 50%
    transform translateX(-50%)
    font-weight 900
    font-size 20px
    line-height 150%
    white-space nowrap
    background #FF4343
    border-radius 30px
    color white
    padding 0 19px 4px
  &__btn
    position absolute
    bottom 15%
    left 50%
    transform translateX(-100%)
.right-side
  display flex
  align-items center
  flex-direction column
  justify-content center
  padding-left 100px
  &__wrapper
    padding-top 64px
    &:first-child
      padding-top 0
  &__number
    font-size 100px
    line-height 89.5%
    text-transform uppercase
  &__text
    padding-top 11px
    font-weight 500
    font-size 30px
    line-height 150%
</style>