<template lang="html">
  <div>
    <ul>
      <list-item v-for="(beer, index) in beers" :beer="beer" :key="index"></list-item>
      <!-- <select v-on:change="handleSelect" v-model="selectedbeer">
      <option disabled value="">Select a beer...</option>
      <option v-for="beer in beers" :value="beer">{{beer.name}}</option>
    </select> -->
    </ul>
  </div>

</template>

<script>
import ListItem from './ListItem.vue';


export default {
  name: 'beers-list',
  props: ['beers'],

  components: {
    "list-item": ListItem
  }
}
</script>

<style lang="css" scoped>
</style>
