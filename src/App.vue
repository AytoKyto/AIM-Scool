<template>
  <div id="app">
    <HelloWorld msg="Welcome to AIM Scool"/>
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
  background-color: whitesmoke;
  margin: 0;
}
</style>
