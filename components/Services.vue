<template>
  <div 
    :class="{'bg-white': serviceContent.background === 'white', 'bg-black': serviceContent.background === 'black', 'bg-pink': serviceContent.background === 'pink'}" 
    class="service">
    <div class="content">
      <div v-if="serviceContent.title" class="title">{{serviceContent.title}}</div>
      <div v-if="serviceContent.subtitle" class="subtitle">{{serviceContent.subtitle}}</div>
      <div v-if="serviceContent.description" class="description">
        <div>
          <p>
            {{serviceContent.description}}
          </p>
          <!-- <p>
            Сегодня Почта России поменялась: очередей на самом деле стало меньше, а большинство операций можно сделать онлайн, но представление осталось. Это и есть бренд.
          </p> -->
        </div>
      </div>
      <div class="column-block">
        <div class="left-column">
          <div class="left-column__top-text" :class="{'big-text': serviceContent.bigTopText}">{{serviceContent.topText}}</div>
          <div v-if="serviceContent.botText">{{serviceContent.botText}}</div>
      </div>
        <div class="right-column">
          <div class="list-block">
            <div v-if="serviceContent.subtitleList" class="list-block__title">{{serviceContent.subtitleList}}</div>
            <ul
              class="list-block__list">
              <li 
                :class="{'list-block__big-list-text': serviceContent.bigTopText, 'white-border': serviceContent.whiteBorder}"
                v-for="(list, index) in serviceContent.list" 
                :key="`${index}-list`"
                class="list-block__item">{{list}}</li>
            </ul>
          </div>
        </div>
      </div>
      <div v-if="serviceContent.buttonsContent" class="under-content">
        <div class="under-content__buttons">
          <Button 
            class="under-content__button"
            v-for="(button, index) in serviceContent.buttonsContent"
            :key="index"
            :buttonContent="button"
           />
        </div>
        <div v-if="serviceContent.image" class="under-content__image">
          <img :src="src" alt="">
        </div>
      </div>
       <div 
        v-if="serviceContent.leftUnderText" 
        class="alternate-under-content">
        <div>{{serviceContent.leftUnderText}}</div>
        <div>{{serviceContent.rightUnderText}}</div>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    serviceContent: {
      type: Object,
      default: null,
    }
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
    }
  }
})
</script>
<style lang="stylus" scoped>
.service
  &.bg-pink
    background #FF4343
    color #fff
  &.bg-white
    background #fff
    color #000
  &.bg-black
    background #000
    color #fff

.content
  padding-top 150px
  padding-bottom 150px
  margin 0 auto
  max-width 1200px

.title
  font-size 100px
  line-height 0.89
  margin-bottom 93px
  text-transform uppercase

.subtitle
  font-weight 500
  font-size 30px
  line-height 1.5
  width 78%
  margin-bottom 61px

.description
  display flex
  justify-content flex-end
  margin-bottom 31px
  div
    width 48%
  p
    font-weight 300
    font-size 20px
    line-height 1.5
.column-block
  display flex
  justify-content space-between

.left-column
  display flex
  flex-direction column
  justify-content space-between
  width 45%
  div
    font-size 30px
    font-weight 500
    line-height 1.5
  & .big-text
    text-transform uppercase
    font-size 100px
    line-height 104.5%

.right-column
  width 48%

.list-block
  position relative
  &__title
    font-size 30px
    font-weight 500 
    line-height 1
    padding-bottom 35px
  &__list
    margin 0
    padding 0
  &__item
    list-style-type none
    padding 35px 0
    border-bottom 1px solid grey
    font-size 20px
    font-weight 300
    line-height 1.5
    &:first-child
      padding-top 0
    &.white-border
      border-bottom 1px solid white
  &__big-list-text
    font-size 30px
    font-weight 500
    line-height 1.5  
  &:before
    content " "
    background grey
    width 1px
    height 100%
    position absolute
    left -40px
.under-content
  margin-top 46px
  &__button
    &:last-child
      margin-left 15px
.alternate-under-content
  display flex
  justify-content space-between
  padding-top 73px
  div
    width 48%
    font-size 20px
    line-height 150%
</style>