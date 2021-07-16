<template>
  <v-content>
    <!-- top banner -->
    <section id="main-banner">
            <banner :person="persons[4]"></banner>
    </section>
    <!-- add section -->
    <add-component></add-component>
    <!-- persons sections -->
    <section id="previous-rulings">
      <v-container>
        <h2>Votes</h2>
        <div class="persons-wrapper">
          <v-row>
            <v-col cols="12" :xs="12" :sm="12" :md="6" v-for="person in persons" :key="person.name">
              <person-component :person="person" @hola="saveVotes"></person-component>
            </v-col>
          </v-row>
        </div>
      </v-container>
    </section>
    <!-- add person section -->
    <add-person-component></add-person-component>
  </v-content>
</template>

<script>
import banner from '../components/main-banner';
import addComponent from '../components/add-component';
import personComponent from '../components/person-component';
import addPersonComponent from '../components/add-person-component';
import DATA from '../utils/Data';

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
      persons: DATA,
    }
  },
  mounted() {
    this.getVotes();
  },
  methods:{
    saveVotes(){
      console.log('hola mundo');
      localStorage.setItem('persons', JSON.stringify(this.persons));
    },
    getVotes(){
      const votes = JSON.parse(localStorage.getItem('persons'));//getting the saved votes
      votes ? this.persons = votes : console.log('no storage');//checking for existing votes
    }
  }
}
</script>
