<template>
  <div class="feedback">
    <div class="wrapper">
      <div class="feedback__more-cases">
        <NuxtLink to="/cases">Смотреть больше кейсов</NuxtLink>
      </div>
      <div class="feedback__title">Про нас тут сказали такооое</div>
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
.wrapper
  margin 0 auto
  max-width 1140px
  padding 45px 0 95px
.feedback
  &__more-cases
    a
      padding 15px 116px
      background #FF4343
      color white
      border-radius 50px
      font-weight 500
      font-size 20px
      line-height 150%
      text-decoration none
    padding-bottom 150px
  &__title
    font-size 100px
    line-height 104.5%
    width 90%
    text-transform uppercase
</style>