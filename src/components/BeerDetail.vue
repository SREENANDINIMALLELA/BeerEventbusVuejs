<template lang="html">
  <div v-if='beer'>
    <h3>{{beer.name}}</h3>
    <button v-on:click ="addToFavourites" > Add to favourite</button>
    <p>{{beer.description}}</p>
    <div id="right">
      <img :src="beer.image_url" :alt="beer.name">
    </div>
  </div>

</template>

<script>
import {eventBus} from '../main.js';
export default {
  name: 'beer-detail',
  props: ['beer'],
  methods:{
    addToFavourites(){
    eventBus.$emit('fav-beers',this.beer)
    }
  }

}
</script>

<style lang="css" scoped>
#right img {
  height: 300px;
  width: 100px;
}
</style>


<!-- <button v-if="!favouriteCountries.includes(selectedCountry)" v-on:click="addToFavourites">Add Country</button> -->
