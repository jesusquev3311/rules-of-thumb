<template>
  <v-app>
    <v-content>
      <header-component></header-component>
      <home></home>
      <!-- footer -->
      <footer>
        <v-container>
          <v-row>
            <v-col :md="8">
              <nav class="footer-nav">
                <ul>
                  <li><a href="#">Terms and Conditions</a></li>
                  <li><a href="#">Privacy Policy</a></li>
                  <li><a href="#">Contact Us</a></li>
                </ul>
              </nav>
            </v-col>
            <v-col :md="4"></v-col>
          </v-row>
        </v-container>
      </footer>
    </v-content>
  </v-app>
</template>

<script>
import home from './views/Home';
import headerComponent from './components/header-component';

export default {
  name: 'App',

  components: {
    home,
    'header-component':headerComponent
  },

  data: () => ({
    //
  }),
};
</script>
<style lang="scss">
  /*default font*/
  @import url('https://fonts.googleapis.com/css2?family=Lato:wght@100;400;700;900&display=swap');
  /**** Default rules ****/
  /*Colors*/
    $green:#1cbbb4;
    $orange:#ffad1d;
    $gray:#333;
    $white:#fff;
  /*typography*/
  *{
    font-family: 'Lato', sans-serif;;
  }
  h1,h2,h3,h4,h5,h6{
    margin: 0;
    padding: 0;
  }
  h1{
    font-size: 58px;
    font-weight: 700;
    line-height: 62px;
    color: $white;
  }
  h2{
    font-size: 38px;
    font-weight: lighter;
    line-height: 45px;
    color:$gray;
  }
  h3{
    font-size: 41px;
    font-weight: lighter;
    line-height: 45px;
    color: $white;
  }

  .text-logo{
    font-size: 26px;
    line-height: 30px;
    font-weight: 700;
    color: $white;
  }
  .bg-orange{background-color: $orange;}
  .bg-green{background-color: $green;}

</style>
