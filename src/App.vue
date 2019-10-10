<template lang="html">
  <div>
    <h1>Beers</h1>
    <div class="main-container">
      <beers-list :beers='beers'></beers-list>
      <beer-detail :beer='selectedbeer'></beer-detail>
    </div>
  </div>

</template>

<script>
import {eventBus} from './main.js';
import BeersList from './components/BeersList.vue';
import BeerDetail from './components/BeerDetail.vue';

export default {
  name: 'app',
  data(){
    return {
      beers: [],
      selectedbeer: null,
      favouriteBeers: []
    };
  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beers => this.beers = beers)
    eventBus.$on('beer-selected',(beer)=> {
      this.selectedbeer=beer;
    })
    eventBus.$on('fav-beers',(beer)=> {
      debugger
      console.log(beer);
      this.favouriteBeers.push(beer)
    })
  },
  components: {
    "beers-list": BeersList,
    "beer-detail": BeerDetail
    },

  }
  </script>

  <style lang="css" scoped>
  </style>
