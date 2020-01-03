<template lang="html">
  <li v-on:click="handleClick">{{beerProp.name}}</li>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'beer-list-item',
  props: ['beerProp'],
  methods: {
    handleClick(){
      eventBus.$emit('selected-beer', this.beerProp)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
