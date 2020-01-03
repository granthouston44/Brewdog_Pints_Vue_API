<template lang="html">
  <ul>
    <beer-list-item v-for="(beer, index) in allBeersProp" :beerProp="beer" :key="index"></beer-list-item>
  </ul>
</template>

<script>
import BeerItem from './BeerItem.vue'
import {eventBus} from '../main.js'

export default {
name: 'beers-list-all',
data(){
  return {
    selectedBeer: null
  }
},
props: ['allBeersProp'],
components: {
  "beer-list-item": BeerItem
},
methods: {
  handleClick(event){
    eventBus.$emit('selected-beer', this.selectedBeer)
  }
}
}
</script>

<style lang="css" scoped>
</style>
