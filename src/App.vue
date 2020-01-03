<template>
  <div id="app">
    <div class="main-container">
      <h1>Aww the pints!</h1>
      <button v-on:click="isHidden = false" type="button" name="button">All</button>
      <beers-list-all v-if="!isHidden" :allBeersProp="beers"/>
      <beers-list :allBeersProp="beers"/>
    </div>
  </div>
</template>

<script>
import BeersList from './components/BeersList.vue'
import BeersListAll from './components/BeersListAll.vue'
import {eventBus} from './main.js'

export default {
  name: 'app',
  data(){
    return {
      beers: [],
      isHidden: true,
      selectedBeer: null
    }
  },
  components: {
    "beers-list": BeersList,
    "beers-list-all": BeersListAll
  },
  methods: {
    handleChange(event){
      console.log('hi from click');;
    }
  },

mounted(){
  fetch("https://api.punkapi.com/v2/beers")
  .then(response => response.json())
  .then(beers => this.beers = beers)

  eventBus.$on('selected-beer', (beer)=>{
    this.selectedBeer = beer
    this.isHidden = true
  })
}


}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
