<template>
<div class="form">
  <div class="form__wrapper">
    <div class="form__title">
      Контакты
    </div>
    <div class="form__wrapper-sides">
    <div class="form__left">
      <div class="form__left-description">
      Будет круто, если вы напишете прежде чем позвонить :) Спасибо! 
      </div>
      <div class="form__left-wrapper">
        <div class="form__left-top">
          <span>+7 928 198 46 10</span>
          <span>телеграм</span>
        </div>
        <div class="form__left-bot">
          <span>kooperativ@mail.ru</span>
          <span>ватсап</span>
        </div>
      </div>
    </div>
    <div class="form__right">
      <div class="form__right-circle"/>
        <!-- @submit="checkForm" -->
      <form
        id="app"
        action="iorinv@list.ru"
        method="post"
        class="form__right-fields"
      >

      <!-- <p v-if="errors.length">
        <b>Пожалуйста исправьте указанные ошибки:</b>
        <ul>
          <li v-for="error in errors">{{ error }}</li>
        </ul>
      </p> -->

      <p>
        <input
          id="name"
          placeholder="Ваше имя"
          type="text"
          name="name"
        >
      </p>

      <p>
        <input
          id="age"
          type="phone"
          placeholder="+7 (___) ___ __ __"
          name="age"
          min="0"
        >
      </p>

      <p>
        <input
          id="movie"
          name="email"
          placeholder="E-mail"
        />

      </p>
      <p>
        <input placeholder="Ваш вопрос или комментарий">
      </p>
      <div class="form__button">
        <Button :buttonContent="button"/>
      </div>

    </form>
    </div>
    </div>
 </div>
</div>
</template>
<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data: () => ({
     button: {
        "color": "black",
        "text": "Что за проект?", 
        "border": "none"
    },
  })
})
</script>
<style lang="stylus" scoped>
::-webkit-input-placeholder  
   color black
:-moz-placeholder 
   color black
::-moz-placeholder  
   color black
:-ms-input-placeholder 
   color black
input, textarea 
  outline none
  border none
  background transparent
  border-bottom 1px solid black
  width 460px
  height 80px
  font-size 20px
  line-height 1.5
  color #000
  &:not(:first-of-type)
    margin-top 30px

.form
  background #F3F3F3
  &__wrapper
    padding 120px 0
    max-width 1190px
    margin 0 auto
    color black
    &-sides
      display flex
      justify-content space-between
      margin-top 70px
  &__button
    display flex
    justify-content center
    margin-top 50px
  &__title
    font-size 87px
    line-height 89.5%
    text-transform uppercase
    color black
  &__right
    position relative
    background transparent
    &-circle
      position absolute
      z-index 5
      background #FF4343
      width 300px
      height 300px
      top 50%
      left 50%
      border-radius 50%
      transform translate3d(-50%, -60%, 0)
    &-fields
      position relative
      z-index 10
  &__left
    &-description
      font-weight 500
      font-size 27px
      line-height 1.5
      width 65%
      margin-top 50px
    &-wrapper
      font-size 20px
      line-height 1.5
      color black
      margin-top 70px
      width 70%
    &-top,
    &-bot
      display flex
      justify-content space-between
    &-bot
      margin-top 35px
      &:last-child
        padding-right 70px
    &-top
      padding-right 70px
</style>
