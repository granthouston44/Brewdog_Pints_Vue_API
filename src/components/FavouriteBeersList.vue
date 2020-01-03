<template lang="html">
  <ul>
    <beer-list-item v-for="(beer, index) in allBeersProp" :beerProp="beer" :key="index"></beer-list-item>
  </ul>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  
}
</script>

<style lang="css" scoped>
</style>
