<template>
  <div class="bigWrapper" v-if="cross">
    <div class="overlay"></div>
    <div class="wrapperModal">
      <div class="modal">
        <p><strong>Your parameters</strong></p>
        <label>Circles size </label>
        <button @click="facile"  type="button">Facile</button>
        <button @click="normal"  type="button">Normal</button>
        <button @click="expert"  type="button">Expert</button>
        <br />
        <br />
        <button @click="crossF" class="btn-modal">Start</button>
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
