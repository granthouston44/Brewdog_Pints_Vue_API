<template lang="html">
  <img :src="getImage"/>
</template>

<script>
export default {
  name: 'beer-image',
  props: ['imageURL'],
  computed: {
      getImage(){
      return this.imageURL
    }
}
}
</script>

<style lang="css" scoped>
</style>
