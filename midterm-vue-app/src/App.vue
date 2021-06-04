<template>
  <header_vue />
  <footer_vue />
</template>

<script>
import header_vue from '@/components/header'
import footer_vue from '@/components/footer'
export default {
  name: 'App',
  components: {
    header_vue,
    footer_vue
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
