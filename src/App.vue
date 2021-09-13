<template>
  <div id="app">
    <Shotvue/>
  </div>
</template>

<script>
import Shotvue from './components/Shotvue.vue'

export default {
  name: 'App',
  components: {
    Shotvue,
  }
}
</script>

<style>
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-image: url(./assets/wall.svg);
  background-position: center;
  background-size: cover;
  margin: 0;
}
</style>
