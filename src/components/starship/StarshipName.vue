<template>
  <div class="starship-name">
    Name: <span>{{name}}</span>
  </div>
</template>

<script>
export default {
  name: 'StarshipName',
  props: {
    name: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.starship-name {
  margin-bottom: 6px;
  span { font-weight: bold; }
}
</style>
