<template>
  <div class="wrapper">
    <Modal
      :cross="cross"
      :crossF="crossF"
      :large="large"
      :limitScore="limitScore"
    />
    <div class="shotWrapper">
      <div :style="styleCirlce" @click="changeDirection" class="circle"></div>
    </div>
    <p class="score">Votre score et de {{ scoreVal }}</p>
  </div>
</template>

<script>
import Modal from "./Modal.vue";

export default {
  name: "Shotvue",
  components: {
    Modal,
  },
  data() {
    return {
      scoreVal: 0,
      limitScore: 20,
      x: 0,
      y: 0,
      large: 20,
      cross: true,
    };
  },
  methods: {
    changeDirection: function () {
      this.scoreVal++;
      if (this.scoreVal < this.limitScore) {
        this.x = Math.random() * 95;
        this.y = Math.random() * 75;
      } else {
        alert("bravo");
      }
    },
    crossF: function () {
      this.cross = !this.cross;
    },
  },
  computed: {
    styleCirlce: function () {
      return {
        marginLeft: this.x + "vw",
        marginTop: this.y + "vh",
        width: this.large + "px",
        height: this.large + "px",
      };
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.shotWrapper {
  border: 4px solid #ED7768;
  border-radius: 10px;
  width: 97vw;
  height: 80vh;
  margin: 0 auto;
  background-color: whitesmoke;
  cursor: cell;
}
.circle {
  border: 1px solid white;
  border-radius: 1000000px;
  background-color: #ED7768;
}
</style>
