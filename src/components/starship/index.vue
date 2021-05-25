<template>
  <div class="starship">
    <div class="starship-contents">
      <div v-if="ship.isMostFrequent" class="ff-badge">Frequent Flyer!</div>
      <StarshipName :name="ship.name" />
      <StarshipModel :model="ship.model" />
      <StarshipNumOfFilms :count="ship.films.length" />
      Crew: {{ship.crew}}
    </div>
  </div>
</template>

<script>
import StarshipName from './StarshipName.vue'
import StarshipModel from './StarshipModel.vue'
import StarshipNumOfFilms from './StarshipNumOfFilms.vue'

export default {
  name: 'Starship',
  components: {
    StarshipName,
    StarshipModel,
    StarshipNumOfFilms
  },
  props: {
    ship: Object
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.starship {
  width: 90%;
  width: calc(100% - 20px);
  padding: 10px;
  border: 1px solid $color-black;
  border-radius: 8px;
  box-shadow: 3px 3px 3px 1px rgba(0, 0, 0, .5);
  overflow: hidden;
  display: inline-block;
  margin: 0 10px 10px 0;
  vertical-align: top;
}
@media (min-width: 768px) {
  .starship {
    width: 200px;
  }
}
@media (min-width: 1440px) {
  .starship {
    width: 300px;
  }
}
.starship > div {
  margin-bottom: 10px;
}
.starship-contents {
  overflow-y: auto;
  margin-bottom: 10px;
  @media (min-width: 1440px) {
    max-height: 200px;
  }
}
.ff-badge {
  background-color: red;
  color: white;
  border-radius: 8px;
  margin-bottom: 10px;
}
</style>
