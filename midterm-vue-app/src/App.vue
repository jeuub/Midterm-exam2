<template>
  <header_vue />
  <list v-bind:items="items" v-model:categorys="categorys"  @remove_item="remove_item" @addItem="addItem"/>
  <footer_vue />
</template>

<script>
import header_vue from '@/components/header'
import footer_vue from '@/components/footer'
import list from '@/components/list'
export default {
  name: 'App',
  components: {
    header_vue,
    footer_vue,
    list
  },
  data(){
    return {
      categorys: [
        {id: 1, name: 'metodologys'},
        {id: 2, name: 'techs'},
        {id: 3, name: 'new'}
        ],
      items: [
        {id:1, title:'bulma', description:'Bulma – отличная альтернатива Bootstrap с современным кодом и уникальной эстетикой. Инструментарий отличается простым синтаксисом, изобилует готовыми компонентами, к тому же его легко импортировать в проекты. Этот фреймворк сделает скучную веб-страницу яркой и привлекательной: более 40000 звезд на GitHub – важный показатель.', category:"metodologys", readed: false, src:''},
        {id:2, title:'bootstrap', description:'Эту платформу создали в Twitter в 2011 году, чтобы сделать адаптивный дизайн доступным для разработчиков. С тех пор проект развился и предлагает бесчисленное множество функций для повышения производительности интерфейса.', category:"techs", readed: false, src:'https://getbootstrap.ru/docs/4.5/assets/brand/bootstrap-social.png'},
        {id:3, title:'UIKit', description:'Модульная структура внешнего интерфейса UIKit позволяет импортировать только нужные функции. У него более 16 тысяч звезд на GitHub, благодаря простому API и чистому дизайну. Существует профессиональная версия UIKit с тематическими страницами для WordPress и Joomla в сочетании с простым в использовании конструктором страниц.', category:"new", readed: false, src:''}
      ]
    }
  },
    methods: {
    remove_item(id){
      console.log(id);
      this.items = this.items.filter(t=> t.id !== id)
    },
    addItem(item){
      this.items.push(item);
    }
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Raleway:wght@400;600&display=swap');
@import 'style/style.css';
#app {
  font-family: 'Raleway', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #3D405B;
}
</style>
