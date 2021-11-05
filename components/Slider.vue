<template>
<div class="slider">
  <div ref="swiperContainer" class="swiper-container">
    <!-- Additional required wrapper -->
      
    <div class="swiper-wrapper">
      <!-- Slides -->
      <div class="swiper-slide">
        <div class="slider__left-side">
            <div class="slider__avatar"></div>
            <div class="slider__info-block">
              <div class="slider__info-name">
                <span>Александра</span>
                <span>Ателье-бутик Kimono Shop</span>
              </div>
              <Button class="slider__button" :buttonContent="button" />
            </div>
          </div>
          <div class="slider__right-side">
            <div class="slider__wrapper-text">
              <span class="slider__text">Это всё потому что раньше мы занимались только SMM, а потом поняли, что упаковывать продукты с помощью сайтов круто, нашли хорошего разработчика и добавили эту услугу тоже. Это всё потому что раньше мы занимались только SMM, а потом поняли, что упаковывать продукты с помощью сайтов круто, нашли хорошего разработчика.
              </span>
            </div>
          </div>
      </div>
      <div class="swiper-slide">Slide 2</div>
      <div class="swiper-slide">Slide 3</div>
    </div>
      <div class="swiper-button-prev">клик</div>
      <div class="swiper-button-next">клик</div>

    <!-- If we need pagination -->
    <!-- <div class="swiper-pagination"></div> -->

    <!-- If we need navigation buttons -->
 

    <!-- If we need scrollbar -->
    <!-- <div class="swiper-scrollbar"></div> -->
  </div>
</div>
</template>

<script lang="ts">
import Vue from 'vue';
import Swiper from 'swiper';
import 'swiper/swiper.min.css';
// import '@/node_modules/swiper/css/swiper.css';


export default Vue.extend({
  name: 'HeaderLink',

  components: {
  },

  props: {
    isIndexPage: {
      type: Boolean,
      default: false,
    },
    content: {
      type: Array,
      default: null,
    },
  },

  data: () => ({
    activeIndex: null,
    // swiperContainer: null as Swiper,
    buttonInfo: [
      { title: 'Ипотека', link: '/ipotecnoe-straxovanie/ipoteka' },
      { title: 'Автомобиль', link: '/avtostraxovanie' },
      { title: 'Путешествие', link: '/straxovanie-putesestviya' },
      { title: 'Жизнь и здоровье', link: '/straxovanie-zizni-i-zdorovya' },
      { title: 'Имущество', link: '/straxovanie-imushhestva' },
    ],
    button: {
        "color": "black",
        "text": "Что за проект?", 
        "border": "none"
      }
  }),

  computed: {
  },

  watch: {
    isTablet() {
      this.initSwiper();
    },
    isMobile() {
      this.initSwiper();
    },
    isDesktop() {
      this.destroySwiper();
    }
  },

  mounted() {
    this.initSwiper();
  },

  beforeDestroy() {
    this.destroySwiper();
  },

  methods: {
    initSwiper() {
       new Swiper(this.$refs.swiperContainer as HTMLElement, {
        direction: 'horizontal',
        slidesPerView: 1,
        slidesPerGroup: 1,
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev',
        },

      });
    },
    destroySwiper() {
      // if (this.swiperContainer) {
      //   this.swiperContainer.destroy(true, true);
      // }
    },
  }
});
</script>

<style lang="stylus">
.header-links
  & .swiper-wrapper
    display flex
    padding-left 7px

</style>

<style lang="stylus" scoped>
.slider
  background #F3F3F3

  &__item
    display flex
    justify-content space-between
    padding 50px 0
    width 100% !important
  &__button
    // bottom 0
    // position absolute
  &__right-side
    width 45%
  &__text
    padding 32px 60px 31px 40px
  &__wrapper-text
    background white
    border-radius 30px
    display flex
    justify-content center
  &__left-side
    display flex
    position relative
  &__avatar
    width 160px
    height 160px
    background grey
    border-radius 100%
  &__info-block
    display flex
    flex-direction column
    justify-content space-between
    margin-left 40px
    line-height 1.5
  &__info-name
    display flex
    flex-direction column
    span
      &:first-child
        font-size 30px
      &:last-child
        font-size 20px
  &__navigation
    position relative
.swiper-container
  display flex
  justify-content center
  overflow hidden
  max-width 1190px
  padding 100px 0
.swiper
  &-wrapper
    position relative
    display flex
  &-button-next
  &-button-prev
    position absolute
    width 40px
    height 40px
    border-radius 50%
    background #FF4343
    bottom 0
    z-index 1000
  &-button-prev
    left 0
  &-button-next
    right 0
  &-slide
    display flex
    justify-content space-between
    padding 2em
</style>
