<template lang="html">
<div v-if="beerProp">
  <h2>{{beerProp.name}}</h2>
  <p>{{beerProp.food_pairing}}</p>
</div>
</template>

<script>


export default {
  name: 'beer-detail',
  props: ['beerProp']
}
</script>

<style lang="css" scoped>
</style>
