<template>
  <div class="header">
    <img class="logo" src="../assets/logo.svg" />
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  display: flex;
  justify-content: center;
  color: white;
  padding-left: 4.5vw;
}
.logo {
  width: 3.5vw;
  margin-right: 1vw;
}
</style>
