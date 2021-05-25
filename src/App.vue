<template>
  <div id="main-container">
    <Main msg="Starships in Vue"/>
  </div>
</template>

<script>
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Main
  }
}
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
  font-family: Helvetica, arial;
  color: #373b3f;
  * {
    box-sizing: border-box;
  }
}

#main-container {
  position: relative;
  margin-top: 45px;
  padding: 20px;
}
</style>
