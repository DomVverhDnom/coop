<template>
<div 
    :class="{opened: opened}"
    class="accordion"
    @click="buttonClick"
  >
    <div 
      class="accordion__header"
    >
      <div class="accordion__title">
        <slot name="title" />
    <div 
      class="accordion__content"
      :style="{maxHeight: opened ? maxHeight : 0}">
      <p ref="content">
        <slot name="content" />
      </p>
    </div>
      </div>
    </div>
</div>
</template>
<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'AccordionBlock',

  data: () => ({
    opened: false,
    maxHeight: null as any
  }),
  mounted () {
    setTimeout(() => {
      this.countMaxHeight()
      console.log(this.maxHeight)
    }, 10)
  },
  methods: {
    countMaxHeight () {
      this.maxHeight = this.$refs.content && `${(this.$refs.content as HTMLElement).getBoundingClientRect().height + 20}px`
    },
    buttonClick (): void {
      this.opened = !this.opened
    }
  }
})
</script>

<style lang="stylus" scoped>
.accordion
  width 100%
  background-color transparent
  transition 0.3s ease-in-out
  color white
  margin-bottom 0
  display flex
  flex-direction column
  overflow hidden
  margin-bottom 10px
  border-bottom 1px solid white
  &__header
    display flex
    justify-content flex-start
    align-items center
    cursor pointer
    position relative
    font-size 3rem
    line-height 1.5
  &__title
    display flex
    flex-direction column
    margin 31px 0px 30px

  &__img
    width 25px
    height 25px
    transition 0.3s
    margin-left 13px
    position absolute
    right 50px
    // transform rotate(180deg)
  &.opened
    transition all .3s
    // background #0F9B91
    .accordion__img
      transform rotate(-90deg)

  &__content
    margin-top 20px
    max-height 0
    overflow hidden
    font-size 20px
    line-height 1.5
    // width calc(100% - 250px)
    transition max-height 0.5s
    p
      padding-bottom 20px
</style>
