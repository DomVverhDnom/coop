<template >
<div class="accordeons">
  <div class="container">
    <div class="accordeons__container">
     <Accordion v-for="(item, index) in data" :key="index" >
        <template #title>
            {{item.title}}
        </template>
        <template #content>
            {{item.content}}
        </template>
     </Accordion>
    </div>
  </div>
</div>
</template>

<script>
import Accordion from '~/components/Accordion.vue'
import Vue from 'vue'

export default Vue.extend({
  name: 'AccordionContainer',
  components: {
    Accordion
  },
  data: () => ({
    data: [
      {
        title: 'Вы, наверное, заметили, что кейсов по веб-разработке маловато?',
        content: 'По своей сути рыбатекст является альтернативой традиционному lorem ipsum, который вызывает у некторых людей недоумение при попытках прочитать рыбу текст. В отличии от lorem ipsum, текст рыба на русском языке наполнит любой макет непонятным смыслом и придаст неповторимый колорит советских времен.'
      },
      {
        title: 'Вы, наверное, заметили, что кейсов?',
        content: 'По своей сути рыбатекст является альтернативой традиционному lorem ipsum, который вызывает у некторых людей недоумение при попытках прочитать рыбу текст. В отличии от lorem ipsum, текст рыба на русском языке наполнит любой макет непонятным смыслом и придаст неповторимый колорит советских времен.'
      },
      {
        title: 'Вы, наверное, заметили, что кейсов?',
        content: 'По своей сути рыбатекст является альтернативой традиционному lorem ipsum, который вызывает у некторых людей недоумение при попытках прочитать рыбу текст. В отличии от lorem ipsum, текст рыба на русском языке наполнит любой макет непонятным смыслом и придаст неповторимый колорит советских времен.'

      }
    ]
  })
})
</script>

<style lang="stylus" scoped>
.accordeons
  background #FF4343
  &__container
    position relative
    &::before
      content ''
      position absolute
      height calc(100% + 50px)
      width 1px
      background white
      left -50px
  .container
    padding 150px 0
    max-width 1200px
    margin 0 auto
</style>