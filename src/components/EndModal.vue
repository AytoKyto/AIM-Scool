<template>
  <div class="bigWrapper" v-if="end">
    <div class="overlay"></div>
    <div class="wrapperModal">
      <div class="modal">
        <p><strong>Bravo votre score est de {{ scoreVal}} en mode {{difficulty}} </strong></p>
        <p>Pésision : {{ clickVal}} clique pour {{ scoreVal}} hit !</p>
        <p>Taux de réussite {{scoreVal / clickVal * 100}}%</p>
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
  color: black;
}
.overlay {
  background-image: url(../assets/blurr.png);
  background-position: top center;
  background-size: cover;
  position: fixed;
  top: 0;
  z-index: 1;
  width: 102vw;
  height: 103vh;
  margin: -15px;
}
</style>
