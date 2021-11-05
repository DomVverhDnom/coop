<template>
  <div>
    <div class="top-header">
      <div class="left-side">
        <h4>
          Главная
        </h4>
        </div>
      <div class="right-side">
        <div 
          v-for="(item, index) of topLinksArray"
          :key="index"
          class="link"
          v-text="item"/>
      </div>
    </div>
    <div class="bottom-header">
      <p
        v-for="(item, index) of botLinksArray"
        :key="index"
        v-text="item"
      />
    </div>
  </div>
</template>
<script>
import Vue from 'vue';

export default Vue.extend({
  data: () => ({
    topLinksArray: ['О кооперативе', 'Услуги +', 'Наши кейсы', 'Отзывы', 'FAQ', 'Контакты'],
    botLinksArray: ['+7 888 888 88 88', 'mail@mail.ru']
  })
  
})
</script>
<style lang='stylus' scoped>
.top-header
  position absolute
  right 0
  left 0
  top 0
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
  top 0
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
</style>