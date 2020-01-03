<template lang="html">
<div v-if="beerProp">
  <h2>{{beerProp.name}}</h2>
  <p>{{beerProp.food_pairing}}</p>
  <beer-image :imageURL="beerProp.image_url"/>
</div>
</template>

<script>
import BeerImage from './BeerImage.vue'

export default {
  name: 'beer-detail',
  props: ['beerProp'],
  components: {
    'beer-image': BeerImage
  }
}
</script>

<style lang="css" scoped>
</style>
