<template lang="html">
  <div>
    <h1>favouriteBeer</h1>
    <ul>

      <list-item v-for="(beer, index) in beers" :beer="beer" :key="index"></list-item>
    </ul>
  </div>

</template>

<script>
import ListItem from './ListItem.vue';


export default {
  name: 'favourite-Beer',
  props: ['beers'],

  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
