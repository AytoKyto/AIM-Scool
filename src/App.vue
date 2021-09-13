<template>
  <div id="app">
    <HelloWorld msg="AIM Test"/>
    <Shotvue/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Shotvue from './components/Shotvue.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Shotvue
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
  background-image: url(./assets/bg.svg);
  background-position: center;
  background-size: cover;
  margin: 0;
}
</style>
