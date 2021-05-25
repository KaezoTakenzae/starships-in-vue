<template>
  <div>
    <Header />
    <h1>{{ msg }}</h1>
    <div class="btnContainer">
      <button v-on:click="getStarships">Get Starships</button>
      <button v-if="starships.length > 1" v-on:click="sortAscending">Sort Ascending</button>
      <button v-if="starships.length > 1" v-on:click="sortDescending">Sort Descending</button>
    </div>
    <div class="starship-container">
      <Starship v-for="starship in starships" v-bind:key="starship.name" :ship="starship" />
    </div>
  </div>
</template>

<script>
import Header from './header'
import Starship from './starship'

export default {
  name: 'Main',
  components: {
    Header,
    Starship
  },
  data() {
    return {
      starships: [],
    };
  },
  methods: {
    getStarships: function() {
      fetch('https://swapi.dev/api/starships/')
        .then(res => {
          return res.json();
        })
        .then(res => {
          let most_frequent = {
            name: '',
            count: 0,
          };
          let starships = res.results.filter(starship => parseInt(starship.crew, 10) <= 10);
          starships.forEach(starship => {
            if (starship.films.length >= most_frequent.count) {
              most_frequent = {
                name: starship.name,
                count: starship.films.length
              };
            }
          });
          starships.forEach(starship => {
            if (starship.films.length === most_frequent.count) {
              starship.isMostFrequent = true;
            } else {
              starship.isMostFrequent = false;
            }
          })
          starships.sort((a, b) => {
            return parseInt(a.crew, 10) > parseInt(b.crew, 10) ? 1 : -1;
          });
          this.starships = starships;
        })
    },
    sortAscending: function() {
      this.starships.sort((a, b) => {
        return parseInt(a.crew, 10) > parseInt(b.crew, 10) ? 1 : -1;
      });
    },
    sortDescending: function() {
      this.starships.sort((a, b) => {
        return parseInt(a.crew, 10) < parseInt(b.crew, 10) ? 1 : -1;
      });
    },
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.btnContainer {
  display: flex;
  max-width: 400px;
  justify-content: space-evenly;
  margin-bottom: 20px;
}
.starship-container {
  text-align: center;
  margin-top: 10px;
}
@media (min-width: 768px) {
  .starship-container {
    display: flex;
  }
}
</style>
