<template lang="html">
  <div class="">
    <hr>
      <p v-on:click="handleClick">{{beerProp.name}}</p>
    <input type="checkbox" v-if:="!beerProp.isFavourite" v-on:click="addFav" :checked="checked">Favourite Pint list </br>
  </div>

</template>

<script>
import {eventBus} from '../main.js'

export default {
  name: 'beer-list-item',
  props: ['beerProp'],
  data(){
    return{
      checked: false
    }
  },
  methods: {
    handleClick(){
      eventBus.$emit('selected-beer', this.beerProp)
    },
    addFav: function(){
      if this.checked = true
      eventBus.$emit('favourite-checkbox', this.beerProp)
      else eventBus.$emit('favourite-removed', this.beerProp)
    },

  }
}
</script>

<style lang="css" scoped>
</style>
