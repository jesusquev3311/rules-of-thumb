<template>
  <v-content>
    <!-- top banner -->
    <banner></banner>
    <!-- add section -->
    <add-component></add-component>
    <!-- persons sections -->
    <section id="previous-rulings">
      <v-container>
        <h2>Votes</h2>
        <div class="persons-wrapper">
          <v-row>
            <v-col :md="6">
              <person-component></person-component>
            </v-col>
            <v-col :md="6">
              <person-component></person-component>
            </v-col>
            <v-col :md="6">
              <person-component></person-component>
            </v-col>
            <v-col :md="6">
              <person-component></person-component>
            </v-col>
          </v-row>
        </div>
      </v-container>
    </section>
    <!-- add person section -->
    <section id="add-person-section">
      <v-container>
        <add-person-component></add-person-component>
      </v-container>
    </section>
  </v-content>
</template>

<script>
import banner from '../components/main-banner'
import addComponent from '../components/add-component'
import personComponent from '../components/person-component'
import addPersonComponent from '../components/add-person-component'
export default {
  name: 'Home',
  components: {
    banner,
    'add-component':addComponent,
    'person-component':personComponent,
    'add-person-component':addPersonComponent
  },
  data(){
    return{
      persons:{
        0:{
          id:1,
          name: 'Pope Francis',
          category:'Religion',
          description:'lorem',
          votes:{
            up:0,
            down:0
          }
        },
        1:{
          id:1,
          name: 'Kanye West',
          category:'Religion',
          description:'lorem',
          votes:{
            up:0,
            down:0
          }
        }
      }
    }
  }
}
</script>
