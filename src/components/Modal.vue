<template>
  <div class="bigWrapper" v-if="cross">
    <div class="overlay"></div>
    <div class="wrapperModal">
      <div class="modal">
        <p><strong>Your parameters</strong></p>
        <label>Circles size </label>
        <button @click="facile" class="btn btn-primary" type="button">Facile</button>
        <button @click="normal" class="btn btn-primary" type="button">Normal</button>
        <button @click="expert" class="btn btn-primary" type="button">Expert</button>
        <br />
        <br />
        <button @click="crossF" class="btn btn-default">Start</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: ["cross", "crossF", "facile", "normal", "expert","difficulty"],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.wrapperModal {
  position: fixed;
  left: 25%;
  width: 50vw;
  padding: 2vw;
  z-index: 999;
  background-color: white;
  border-radius:10px;
}
.overlay {
  background-color: rgba(0, 0, 0, 0.769);
  position: fixed;
  top: 0;
  z-index: 1;
  width: 100vw;
  height: 100vh;
}
</style>
<style>
.btn {
  border: 1px solid #ed7768;
  color:#ed7768;
  padding: 5px;
  border-radius: 1000000px;
  background-color:white;
  font-size: 1.2em;
  margin: 5px;
  width: 150px;
}
.btn-default{
  color:white;
  background-color:#ed7768;
}

.btn:hover{
  color:white;
  background-color:#ed7768;
}
.btn-default:hover{
  color:#ed7768;
  background-color:white;
}
</style>
