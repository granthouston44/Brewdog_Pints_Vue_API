<template lang="html">
  <div class="">


    <select @change="handleChange" v-model="selectedBeer">
      <option v-for="(beer, index) in allBeersProp" :value="beer" :key="index">{{beer.name}}</option>
    </select>
  </div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'beers-list',
  data(){
    return {
      selectedBeer: null
    }
  },
  props: ['allBeersProp'],
  components: {
    // "beer-item": BeerItem
  },
  methods: {
    handleChange(event){
      eventBus.$emit('selected-beer',this.selectedBeer)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
