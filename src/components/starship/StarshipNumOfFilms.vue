<template>
  <div class="starship-nof">
    Seen in <span>{{count}}</span> {{count === 1 ? 'film' : 'films'}}
  </div>
</template>

<script>
export default {
  name: 'StarshipNumOfFilms',
  props: {
    count: Number
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.starship-nof {
  margin-bottom: 6px;
  span { font-weight: bold; }
}
</style>
