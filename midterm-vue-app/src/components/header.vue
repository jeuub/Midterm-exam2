<template>
  <header class="header">
    <picture class="header__picture">
          <source srcset="../../public/logo.png " type="image/png" media="(min-width:1200px)">
          <source srcset="../../public/logo.png " type="image/png" media="(min-width:768px)">
          <img src="../../public/logo.png" height="60" width="60" alt="logo">
      </picture>
    <span class="header__logo">My midterm exam. Web-tech's</span>
      
    <nav class="header__nav">
      <ul class="header__nav__ul">
        <li class="header__nav__ul__item">
          <a href="#" class="header__nav__ul__item__link">Главная</a>
        </li>
        <li class="header__nav__ul__item">
          <a href="#" class="header__nav__ul__item__link">Меню</a>
        </li>
        <li class="header__nav__ul__item">
          <a href="#" class="header__nav__ul__item__link">О нас</a>
        </li>
      </ul>
    </nav>
    <div style="display: flex">
    <button class="header__changetheme-btn" v-on:click="changeTheme">theme</button>
    </div>
  </header>
</template>
<style Lang="scss">
</style>
<script>
  export default{
    data(){
      return{
        darkmode: true
      }
      
    },
    methods: {
      changeTheme: function(){
        let bodyStyles = document.body.style;
        if(this.darkmode) {
          bodyStyles.setProperty('--white', '#3D405B');
          bodyStyles.setProperty('--dark', '#F4F1DE');
          this.darkmode = false;
        }else {
          bodyStyles.setProperty('--dark', '#3D405B');
          bodyStyles.setProperty('--white', '#F4F1DE');
          this.darkmode = true;
        }
      }
    }
  }
</script>