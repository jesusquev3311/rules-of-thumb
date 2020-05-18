<template>
  <v-app>
    <v-content>
      <header-component @mobile="showMenu"></header-component>
      <home></home>
      <!-- footer -->
      <footer-component></footer-component>
      <!-- mobile menu -->
      <nav id="mobile-menu" :class="{show:this.menu.active}">
        <v-icon id="mobile-close" @click="showMenu">far fa-times-circle</v-icon>
        <ul>
          <li><a href="#"><v-icon>fas fa-search</v-icon></a></li>
          <li><a href="#">Past Trials</a></li>
          <li><a href="#">How It Works</a></li>
          <li class="login-wrapper"><a href="#">Log In</a><a href="#">Sign Up</a></li>
        </ul>
      </nav>
    </v-content>
  </v-app>
</template>

<script>
import home from './views/Home';
import headerComponent from './components/header-component';
import footerComponent from './components/footer-component';

export default {
  name: 'App',

  components: {
    home,
    'header-component':headerComponent,
    'footer-component':footerComponent
  },
  data(){
    return{
      menu:{
        active:false
      }
    }
  },
methods:{
  showMenu(){
    //toggling menu
    this.menu.active = !this.menu.active;
  }
}
};
</script>
<style lang="scss">

  /*default font*/
  @import "assets/sass/style";

</style>
