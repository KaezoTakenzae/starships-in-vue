<template>
  <header>
      <button v-on:click="scrollTop">Home</button>
  </header>
</template>

<script>

export default {
  name: 'Header',
  methods: {
    scrollTop: function() {
      document.body.scrollTop = 0;
      document.documentElement.scrollTop = 0;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
header {
  padding: 10px 20px;
  background-color: #373b3f;
  color: #fff;
  height: 45px;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1;
}
header button {
    color: #fff;
    text-decoration: underline;
    display: inline-block;
    margin-top: 4px;
    background-color: transparent;
    border-width: 0;
}
</style>
