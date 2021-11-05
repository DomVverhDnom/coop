<template>
  <div class="cases">
    <HeaderMenu />
    <div class="cases__red-block"> <span> это кейсы! </span> </div>
    <div class="cases__tabs-wrapper">
      <div class="cases__tabs">
        <span 
          class="cases__tab"
          :class="{active: index === activeTab}"
          @click="setActiveTab(index)"
          v-for="(item, index) in tabs"
          :key="index"
        >{{ item }}</span>
      </div>
    </div>
    <CaseCard />
    <div class="divider" />
    <CaseCard />
    <div class="divider" />
    <CaseCard />
    <Footer />

  </div>
</template>
<script>
import Vue from 'vue'
export default Vue.extend({
  data: () => ({
    activeTab: 0,
    tabs: ['Все кейсы', 'SMM & Соцсети', 'Дизайн', 'Разработка сайтов']
  }),
  methods: {
    setActiveTab(index) {
      this.activeTab = index 
    }
  }
})
</script>
<style lang="stylus" scoped>
.divider 
  height 20px
  position relative
  &:after
    content ''
    position absolute 
    background #F3F3F3
    top 50%
    transform translateY(-100%)
    width 100%
    height 1px
.cases
  &__red-block
    position relative
    font-size 100px
    color white
    text-transform uppercase
    margin-top 65px
    width 550px
    height 550px
    background #FF4343
    span
      position absolute
      top 50%
      left 50%
      transform translate3d(-30%, -50%, 0)
      width fit-content
  &__tabs-wrapper
    background #000
  &__tabs
    display flex
    justify-content space-between
    max-width 1200px
    margin 0 auto
    padding 30px 0
  &__tab
    color white
    font-size 20px
    line-height 1.5
    font-weight 300
    cursor pointer
    &.active
      color red
      text-decoration underline
</style>