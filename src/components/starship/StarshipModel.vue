<template>
  <div class="starship-model">
    Model: <span>{{model}}</span>
  </div>
</template>

<script>
export default {
  name: 'StarshipModel',
  props: {
    model: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.starship-model {
  margin-bottom: 6px;
  span { font-weight: bold; }
}
</style>
