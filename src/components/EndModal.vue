<template>
  <div class="bigWrapper" v-if="end">
    <div class="overlay"></div>
    <div class="wrapperModal">
      <div class="modal">
        <p><strong>Bravo votre score est de {{ scoreVal}} en mode {{difficulty}} </strong></p>
        <p>Pésision : {{ clickVal}} clique pour {{ scoreVal}} hit !</p>
        <p>Présition à {{scoreVal / clickVal * 100}}%</p>
        <form>
        <button type="submit" @click="window.location.reload();" class="btn btn-default">Restart</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "EndModal",
  props: ["end","scoreVal","clickVal","difficulty"],
  data() {
    return {
      result: 0,
    };
  },
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
  border-radius:10px;
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
