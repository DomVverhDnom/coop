<template>
  <div class="price">
    <div class="price__wrapper">
    <div class="title">Сколько это стоит?</div>
    <div class="tabs">
      <div
       v-for="(item, index) in tabs"
       :key="index"
       :class="{'active': indexTab === index}"
       @click="selectTab(item, index)"
       class="tab">{{item.tab}}</div>
    </div>
    <div
      v-for="(card, index) in contentFactory()"
      :key="index" 
      class="cards__wrapper">
      <PriceCard  :content="card.first"/>
      <PriceCard  :content="card.second"/>
      <PriceCard  :content="card.third"/>
      <div v-if="activeTab == 'all'" class="all">
        <div class="all_top">
          <div style="color: red;">all inclusive</div>
           <div style="color: red;">all inclusive</div>
            <div style="color: red;">all inclusive</div>
             <div style="color: red;">all inclusive</div>
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
  mounted() {
    if (this.$route.query && this.$route.query.link) {
      (this.activeTab as any) = this.$route.query.link
    }
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
    activeTab: null,
    indexTab: 0,
    tabs: [
      { tab: 'SMM', link: 'smm' },
      { tab: 'Таргетированная реклама', link: 'target' },
      { tab: 'Брендинг', link: 'branding' },
      { tab: 'Разработка сайтов', link: 'development' },
      { tab: 'Всё и сразу', link: 'all' },
    ],
    button: {
        "color": "black",
        "text": "Что за проект?", 
        "border": "none"
    },
    cardsContentSMM: [
      {
        first: {
            'tarif': "тариф 1",
            'title': "Ведение аккаунта",
            'text': [
              'Разработка SMM-стратегии', 
              'Контент-план на 30 публикаций в месяц', 
              'Визуал & текст Создание и публикация историй: 1-3 в день / не менее 40 в месяц', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов'],
            'topPrice': "45 000 ₽",
            'topDescription': "Рекламный бюджет:",
            'botPrice': "от 10 000 ₽*", 
            'botDescription': "*согласовывается на старте и оплачивается отдельно"

        }, 
        second: {
             'tarif': "тариф 1",
            'title': "Ведение аккаунта",
            'text': [
              'Разработка SMM-стратегии', 
              'Контент-план на 30 публикаций в месяц', 
              'Визуал & текст Создание и публикация историй: 1-3 в день / не менее 40 в месяц', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов'],
            'topPrice': "45 000 ₽",
            'topDescription': "Рекламный бюджет:",
            'botPrice': "от 10 000 ₽*", 
            'botDescription': "*согласовывается на старте и оплачивается отдельно"

        }, 
        third: {
               'tarif': "тариф 1",
            'title': "Ведение аккаунта",
            'text': [
              'Разработка SMM-стратегии', 
              'Контент-план на 30 публикаций в месяц', 
              'Визуал & текст Создание и публикация историй: 1-3 в день / не менее 40 в месяц', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов'],
            'topPrice': "45 000 ₽",
            'topDescription': "Рекламный бюджет:",
            'botPrice': "от 10 000 ₽*", 
            'botDescription': "*согласовывается на старте и оплачивается отдельно"

        }
      }
    ],
    cardsContentTarget: [
      {
        first: {
            'tarif': "тариф 15",
            'title': "Ведение аккаунта",
            'text': [
              'Контент-план на 30 публикаций в месяц', 
              'Визуал & текст Создание и публикация историй: 1-3 в день / не менее 40 в месяц', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Разработка SMM-стратегии', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов'],
            'topPrice': "45 000 ₽",
            'topDescription': "Рекламный бюджет:",
            'botPrice': "от 10 000 ₽*", 
            'botDescription': "*согласовывается на старте и оплачивается отдельно"

        }, 
        second: {
             'tarif': "тариф 1",
            'title': "Ведение аккаунта",
            'text': [
              'Разработка SMM-стратегии', 
              'Контент-план на 30 публикаций в месяц', 
              'Визуал & текст Создание и публикация историй: 1-3 в день / не менее 40 в месяц', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов'],
            'topPrice': "45 000 ₽",
            'topDescription': "Рекламный бюджет:",
            'botPrice': "от 10 000 ₽*", 
            'botDescription': "*согласовывается на старте и оплачивается отдельно"

        }, 
        third: {
               'tarif': "тариф 1",
            'title': "Ведение аккаунта",
            'text': [
              'Разработка SMM-стратегии', 
              'Контент-план на 30 публикаций в месяц', 
              'Визуал & текст Создание и публикация историй: 1-3 в день / не менее 40 в месяц', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов'],
            'topPrice': "45 000 ₽",
            'topDescription': "Рекламный бюджет:",
            'botPrice': "от 10 000 ₽*", 
            'botDescription': "*согласовывается на старте и оплачивается отдельно"

        }
      }
    ],
    cardsContentBranding: [
      {
        first: {
            'tarif': "тариф 1",
            'title': "Ведение аккаунта",
            'text': [
              'Разработка SMM-стратегии', 
              'Контент-план на 30 публикаций в месяц', 
              'Визуал & текст Создание и публикация историй: 1-3 в день / не менее 40 в месяц', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов'],
            'topPrice': "45 000 ₽",
            'topDescription': "Рекламный бюджет:",
            'botPrice': "от 10 000 ₽*", 
            'botDescription': "*согласовывается на старте и оплачивается отдельно"

        }, 
        second: {
             'tarif': "тариф 1",
            'title': "Ведение аккаунта",
            'text': [
              'Разработка SMM-стратегии', 
              'Контент-план на 30 публикаций в месяц', 
              'Визуал & текст Создание и публикация историй: 1-3 в день / не менее 40 в месяц', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов'],
            'topPrice': "45 000 ₽",
            'topDescription': "Рекламный бюджет:",
            'botPrice': "от 10 000 ₽*", 
            'botDescription': "*согласовывается на старте и оплачивается отдельно"

        }, 
        third: {
               'tarif': "тариф 1",
            'title': "Ведение аккаунта",
            'text': [
              'Разработка SMM-стратегии', 
              'Контент-план на 30 публикаций в месяц', 
              'Визуал & текст Создание и публикация историй: 1-3 в день / не менее 40 в месяц', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов'],
            'topPrice': "45 000 ₽",
            'topDescription': "Рекламный бюджет:",
            'botPrice': "от 10 000 ₽*", 
            'botDescription': "*согласовывается на старте и оплачивается отдельно"

        }
      }
    ],
    cardsContentDevelopment: [
      {
        first: {
            'tarif': "тариф 1",
            'title': "Ведение аккаунта",
            'text': [
              'Разработка SMM-стратегии', 
              'Контент-план на 30 публикаций в месяц', 
              'Визуал & текст Создание и публикация историй: 1-3 в день / не менее 40 в месяц', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов'],
            'topPrice': "45 000 ₽",
            'topDescription': "Рекламный бюджет:",
            'botPrice': "от 10 000 ₽*", 
            'botDescription': "*согласовывается на старте и оплачивается отдельно"

        }, 
        second: {
             'tarif': "тариф 1",
            'title': "Ведение аккаунта",
            'text': [
              'Разработка SMM-стратегии', 
              'Контент-план на 30 публикаций в месяц', 
              'Визуал & текст Создание и публикация историй: 1-3 в день / не менее 40 в месяц', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов'],
            'topPrice': "45 000 ₽",
            'topDescription': "Рекламный бюджет:",
            'botPrice': "от 10 000 ₽*", 
            'botDescription': "*согласовывается на старте и оплачивается отдельно"

        }, 
        third: {
               'tarif': "тариф 1",
            'title': "Ведение аккаунта",
            'text': [
              'Разработка SMM-стратегии', 
              'Контент-план на 30 публикаций в месяц', 
              'Визуал & текст Создание и публикация историй: 1-3 в день / не менее 40 в месяц', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов', 
              'Усиление 15 публикаций в Instagram: продвижение самых активных постов'],
            'topPrice': "45 000 ₽",
            'topDescription': "Рекламный бюджет:",
            'botPrice': "от 10 000 ₽*", 
            'botDescription': "*согласовывается на старте и оплачивается отдельно"

        }
      }
    ]
  }),

  computed: {

  },
  methods: {
     selectTab(item: any, index: number) {
      const query = { ...this.$route.query };
      query.link = item.link;
      this.activeTab = item.link;
      this.$router.push({query})
      this.indexTab = index
      console.log(this.activeTab)
      // if (this.activeTab === 'news') this.$accessor.pressCenter.getAllNews({ page: 1, overwrite: true });
      // if (this.activeTab === 'mass-media') this.$accessor.pressCenter.getAllReview({ page: 1, overwrite: true });
      },
      contentFactory():any {
        switch(this.activeTab as any){
          case 'smm':
            return this.cardsContentSMM;
          case 'target':
            return this.cardsContentTarget;
          case 'branding':
            return this.cardsContentBranding;
          case 'development':
            return this.cardsContentDevelopment;
          
        }        
      }

  }

});
</script>

<style lang="stylus">
.price
  background #000
  color white
.price__wrapper
  padding 150px 0
  max-width 1190px
  margin 0 auto
.title
  font-size 100px
  line-height 104.5%
  width 55%
  text-transform uppercase
.tabs
  display flex
  justify-content space-between
  padding-top 93px
.tab
  cursor pointer
  font-size 20px
  font-weight 300
  line-height 150%
  transition color 0.3s
  &:hover
    transition color 0.3s
    color #FF4343
  &.active
    color #FF4343
.cards__wrapper
  display flex
  justify-content space-between
  margin-top 75px
</style>