<template lang="html">
  <div class="">
    <hr>
      <p v-on:click="handleClick">{{beerProp.name}}</p>
  </div>

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
