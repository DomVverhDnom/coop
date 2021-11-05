<template>
  <div class="card">
     <div class="card__wrapper">
       <div class="wrapper-tags">
       <div v-if="content.tarif" class="card__tags">
         <span>{{ content.tarif }}</span>
       </div>
       </div>
       <div class="card__content">
         <div class="wrapper">
         <div class="card__title">
           {{ content.title }}
         </div>
         <div class="card__description">
           <ul>
             <li 
              v-for="(item, index) in content.text"
              :key="index"
              >{{item}}</li>
           </ul>
         </div>
         </div>
         <div class="card__prices">
           <div class="card__top-price">
             {{content.topPrice}}
           </div>
           <div v-if="content.topDescription" class="card__top-description">
             {{content.topDescription}}
           </div>
           <div v-if="content.botPrice" class="card__bot-price">
             {{content.botPrice}}
           </div>
           <div v-if="content.botDescription" class="card__bot-description">
             <p>
              {{content.botDescription}}
             </p>
           </div>
           <div class="card__button">
            <Button :buttonContent="button"/>
           </div>
         </div>
       </div>
     </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';


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
      type: Object,
      default: null,
    },
  },

  data: () => ({
    tabs: [
      { tab: 'SMM', link: '/ipotecnoe-straxovanie/ipoteka' },
      { tab: 'Таргетированная реклама', link: '/avtostraxovanie' },
      { tab: 'Брендинг', link: '/straxovanie-putesestviya' },
      { tab: 'Разработка сайтов', link: '/straxovanie-zizni-i-zdorovya' },
      { tab: 'Всё и сразу', link: '/straxovanie-imushhestva' },
    ],
     button: {
        "color": "black",
        "text": "Выбрать", 
        "border": "none"
      }
  }),

  computed: {
  },

});
</script>

<style lang="stylus">
.wrapper-tags
  padding 0 45px 0px 45px
.wrapper
  padding 0px 45px 0
.card
  padding-top 25px
  padding-bottom 15px
  background #CACACA
  border-radius 30px
  transition transform .3s, background .3s
  cursor pointer
  &:not(:first-child)
    margin-left 10px
  &:hover
    transition transform .3s, background .3s
    transform scaleY(1.05)
    background #F3F3F3
    // padding-top 50px
    // padding-bottom 50px
  &__tags
    color #FF4343
    font-size 20px
    line-height 0.9
    padding-bottom 35px
    span 
      padding 8px 16px 8px 19px
      border 1px solid #FF4343
      border-radius 30px
  &__title
    font-weight 500
    font-size 33px
    line-height 1.1
    color black
    padding-bottom 25px
    border-bottom 1px solid #797979
  &__description
    bolor black
    padding-top 35px
    ul
      padding 0
    li
      line-height 1.3
      font-size 16px
      list-style-type none
      padding-bottom 30px
      color black
  &__prices
    margin 0 15px 0
    padding 30px 30px 15px 30px
    display flex
    justify-content center
    flex-direction column
    align-items center
    background rgba(255, 255, 255, 0.5)
    border-radius 30px
    color black
  &__top-price
    font-size 30px
    font-weight 500
    line-height 1.5
    text-align center
  &__top-description
    font-size 16px
    line-height 1.3
    padding-top 30px
  &__bot-price
    font-weight 500
    font-size 30px
    line-height 1.5
  &__bot-description
    font-size 16px
    line-height 1.3
    opacity 0.5
    padding-bottom 30px
    p
      text-align center
  
</style>