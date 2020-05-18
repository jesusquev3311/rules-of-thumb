<template>
  <v-app>
    <v-content>
      <header-component></header-component>
      <home></home>
      <!-- footer -->
      <footer-component></footer-component>
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

  data: () => ({
    //
  }),
};
</script>
<style lang="scss">

  /*default font*/
  @import "assets/sass/style";

</style>
