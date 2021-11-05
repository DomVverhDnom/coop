<template>
  <button
    :class="{'black': buttonContent.color === 'black', 'white': buttonContent.color === 'white', 'no-border': buttonContent.border === 'none'}" 
    class="button">
    <span 
      :class="{'white-text': buttonContent.color === 'black', 'black-text': buttonContent.color === 'white'}"
      class="button-text">
      {{buttonContent.text}}
    </span>
  </button>
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
.button
  box-sizing border-box
  border-radius 50px
  padding 15px 55px
  transition transform 0.3s

  &.black
    background #000
    border 1px solid #fff
  &.white
    border 1px solid #000
    background #fff
  &.no-border
    border none
  &-text
    font-weight 500
    font-size 20px
    line-height 1.5
    white-space nowrap
    &.black-text
      color #000
    &.white-text
      color #fff
  &:active
    transition transform 0.3s
    transform scale(1.1)

  
</style>