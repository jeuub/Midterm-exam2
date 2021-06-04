<template>
  <header_vue />
  <list v-bind:items="items" v-model:categorys="categorys" />
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
        {id:1, title:'html', description:'asdasdasdasd', category:"metodologys", readed: true},
        {id:2, title:'css', description:'asdasdasdasd', category:"techs", readed: true},
        {id:3, title:'js', description:'asdasdasdasd', category:"new", readed: true}
      ]
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
