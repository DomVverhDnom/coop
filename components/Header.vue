<template>
  <div class="header">
    <HeaderMenu />
    <div class="logo-content">
      <div class="logo-content__wrapper">
        <div class="smm-phantom">
          <span class="phantom">SMM</span>
        </div>
        <div class="target-phantom">
          <span class="phantom">Таргет</span>
        </div>
        <div class="circe-animation">
          <svg class="svg position-1" width="742" height="406" viewBox="0 0 742 406" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path class="circle anim-delay-1" d="M711.596 111.629C715.694 126.925 710.135 144.076 696.479 162.019C682.825 179.958 661.105 198.65 632.97 217.003C576.704 253.707 494.833 289.026 400.694 314.251C306.556 339.475 217.994 349.823 150.913 346.169C117.372 344.342 89.2154 339.015 68.4214 330.306C47.6234 321.596 34.2337 309.522 30.1351 294.226C26.0365 278.93 31.5956 261.779 45.2519 243.836C58.9056 225.897 80.6261 207.206 108.761 188.852C165.027 152.148 246.898 116.829 341.037 91.6046C435.175 66.3803 523.737 56.0318 590.817 59.6857C624.359 61.5128 652.515 66.84 673.309 75.5489C694.107 84.2594 707.497 96.333 711.596 111.629Z" stroke="#FF4343" stroke-width="0.5"/>
          </svg>
          <svg class="svg position-2" width="742" height="406" viewBox="0 0 742 406" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path class="circle anim-delay-2" d="M711.596 111.629C715.694 126.925 710.135 144.076 696.479 162.019C682.825 179.958 661.105 198.65 632.97 217.003C576.704 253.707 494.833 289.026 400.694 314.251C306.556 339.475 217.994 349.823 150.913 346.169C117.372 344.342 89.2154 339.015 68.4214 330.306C47.6234 321.596 34.2337 309.522 30.1351 294.226C26.0365 278.93 31.5956 261.779 45.2519 243.836C58.9056 225.897 80.6261 207.206 108.761 188.852C165.027 152.148 246.898 116.829 341.037 91.6046C435.175 66.3803 523.737 56.0318 590.817 59.6857C624.359 61.5128 652.515 66.84 673.309 75.5489C694.107 84.2594 707.497 96.333 711.596 111.629Z" stroke="#FF4343" stroke-width="0.5"/>
          </svg>
          <svg class="svg position-3" width="742" height="406" viewBox="0 0 742 406" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path class="circle anim-delay-3" d="M711.596 111.629C715.694 126.925 710.135 144.076 696.479 162.019C682.825 179.958 661.105 198.65 632.97 217.003C576.704 253.707 494.833 289.026 400.694 314.251C306.556 339.475 217.994 349.823 150.913 346.169C117.372 344.342 89.2154 339.015 68.4214 330.306C47.6234 321.596 34.2337 309.522 30.1351 294.226C26.0365 278.93 31.5956 261.779 45.2519 243.836C58.9056 225.897 80.6261 207.206 108.761 188.852C165.027 152.148 246.898 116.829 341.037 91.6046C435.175 66.3803 523.737 56.0318 590.817 59.6857C624.359 61.5128 652.515 66.84 673.309 75.5489C694.107 84.2594 707.497 96.333 711.596 111.629Z" stroke="#FF4343" stroke-width="0.5"/>
          </svg>
        </div>
        <div class="top-text">
            <span>digital-объединение</span>
        </div>
        <div class="center-text">
          <span>КООПЕРАТИВ</span>
        </div>
        <div class="bottom-text">
          <span>Мы кое-что умеем</span>
        </div>
      </div>
    </div>
    <div class="buttons-wrapper">
      <div class="phantom-wrapper">
        <span class="phantom">Брендиг</span>
        <span class="phantom">Веб-дизайн</span>
      </div>
      <div class="buttons">
        <Button 
        v-for="(item, index) in buttonsContent"
        :key="index"
        :buttonContent="item" />
      </div>
    </div>
    <div class="about-us">
      <div class="about-us__title">О нас:</div>
      <div class="about-us__description">Это мы — 6 специалистов, объединившихся в кооператив, чтобы делать дела.</div>
    </div>
    <div class="about-us-text">
      <div class="about-us-text__description">Мы не используем продающие заголовки, не приукрашиваем кейсы и не считаем себя спасателями вашего бизнеса, потому что как-то раз мы нашли в себе смелость быть искренними, а теперь не можем по-другому. </div>
      <div class="about-us-text__description">Часть того, что мы умеем, есть ниже. Там же — кейсы, отзывы и способы связи: напишите или позвоните нам и расскажите про свой проект. Мы точно сработаемся, и вместе сможем больше!</div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue, { PropOptions } from 'vue';
import Button from '@/components/Button.vue'
import HeaderMenu from '@/components/HeaderMenu.vue'

export default Vue.extend({
  name: 'AppTitle',
  components: {
    Button,
    HeaderMenu,
  },
  props: {
    content: {
      type: Object,
      default: null,
    },
  },

  data() {
    return {
      buttonsContent: [
        {
        'color': 'black',
        'text': 'Хочу сотрудничать' 
        },
        {
        'color': 'white',
        'text': 'Что умеете?' 
        }
      ],
      topLinksArray: ['О кооперативе', 'Услуги +', 'Наши кейсы', 'Отзывы', 'FAQ', 'Контакты'],
      botLinksArray: ['+7 888 888 88 88', 'mail@mail.ru']
    };
  },

  computed: {
  },
});
</script>

<style lang="stylus" scoped>
.header
  min-height 100vh
  margin 0 auto
  max-width 1200px
  padding-bottom 150px
.about-us-text
  display flex
  justify-content space-between
  margin-top 5%
.about-us-text__description
  width 49.5%
  margin-right 55px
  font-size 20px
  line-height 1.5
  font-weight 300
.about-us
  display flex
  justify-content space-between
  margin-top 5%
.about-us__title
  text-transform uppercase
  font-size 100px
  line-height 89.5%
  color black
.about-us__description
  position relative
  font-weight 500
  font-size 30px
  line-height 1.5
  width 50%
  &:before
    content " "
    background black
    width 1px
    height 82%
    position absolute
    left -20px
    top 14px
.phantom-wrapper
  display flex
  justify-content space-between
  text-transform uppercase
  span:first-child
    margin-right 120px
.buttons
  display flex
  button:last-child
    margin-left 15px

.buttons-wrapper
  display flex
  justify-content space-between
  align-items flex-end
  padding-top 150px
  margin 0 auto
  max-width 1030px
  &:nth-child(3)
    margin-right 0
.top-header
  position absolute
  right 0
  left 0
  display flex
  justify-content space-between
.left-side
  display flex
  justify-content flex-end
  position relative
  height 65px
  width 235px
  border-radius 0 30px 30px 0
  background black
  cursor pointer
  h4
    position absolute
    color white
    text-transform uppercase
    font-size 15px
    line-height 1.5
    top 19px
    right 25%
.right-side
  display flex
  padding-right 141px
  .link 
    font-weight 500
    padding-top 19px
    padding-bottom 22px
    font-size 16px
    line-height 1.5
    text-transform uppercase
    &:not(:first-child)
      padding-left 39px
.bottom-header 
  display flex
  // justify-content flex-end
  position absolute
  right 0
  background-color #F3F3F3
  margin-top 60px
  border-radius 30px 0 0 30px
  p
    font-weight 500
    font-size 16px
    line-height 1.5
    padding 12px 141px 7px 0
    // padding-right 141px 
  p:first-child
    padding-right 201px
    padding-left 51px
.logo-content
  display flex
  justify-content center
  text-transform uppercase
  padding-top 190px
  &__wrapper
    position relative

.top-text, .bottom-text
  font-weight 500
  font-size 30px
  line-height 1.5


.bottom-text
  position absolute
  right 0  
.center-text
  font-size 98px
  line-height 98.5%
  font-weight bold
.smm-phantom
  display flex
  position absolute
  right 0
.target-phantom
  display flex
  position absolute
  right -185px
.phantom
  font-weight 500
  font-size 30px
  line-height 1.5
  color #E2E2E2
// Анимация серклов
.svg
  position absolute
  z-index 1
.position-1
  z-index -100
  top -100%
  left -34%
.position-2
  z-index -100
  top -80%
  left -33%
.position-3
  z-index -100
  top -60%
  left -32%
.anim-delay-1
  opacity 0
  animation circle-anim 4s 1 ease forwards
  animation-delay 0.5s
.anim-delay-2
  opacity 0
  animation circle-anim 3.3s 1 ease forwards
  animation-delay 1s
.anim-delay-3
  opacity 0
  animation circle-anim 2.5s 1 ease forwards
  animation-delay 1.5s
.circle
  // opacity 0
  stroke-dashoffset 2000
  // animation circle-anim 8s 1 ease forwards

@keyframes circle-anim
  0%
    opacity 1
    stroke-dashoffset 2000
    stroke-dasharray 0

  100%
    opacity 1
    stroke-dashoffset 0
    stroke-dasharray 2000
</style>
