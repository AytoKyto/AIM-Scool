<template>
  <div class="header">
    <img class="logo" src="../assets/logo.svg" />
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  display: flex;
  justify-content: center;
}
.logo {
  width: 5vw;
  margin-right: 1vw;
}
</style>
