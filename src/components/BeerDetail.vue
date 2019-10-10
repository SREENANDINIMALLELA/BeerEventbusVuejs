<template lang="html">
  <div v-if='beer'>
    <h3>{{beer.name}}</h3>
    <p>{{beer.description}}</p>
    <div id="right">
          <img :src="beer.image_url" :alt="beer.name">
        </div>
  </div>

</template>

<script>
export default {
  name: 'beer-detail',
  props: ['beer']
}
</script>

<style lang="css" scoped>
#right img {
  height: 80%;
  width: 20%;
}
</style>
