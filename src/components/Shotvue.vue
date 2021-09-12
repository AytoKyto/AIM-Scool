<template>
  <div class="wrapper">
    <Modal
      :cross="cross"
      :crossF="crossF"
      :facile="facile"
      :normal="normal"
      :expert="expert"
    />
    <EndModal 
    :end="end"
    :scoreVal="scoreVal"
    />
    <div class="shotWrapper">
      <div :style="styleCirlce" @click="changeDirection" class="circle"></div>
    </div>
    <p class="score">Votre score et de {{ scoreVal }}</p>
    <circular-count-down-timer
      v-if="timer"
      :initial-value="10"
      :steps="400"
      :size="150"
      @finish="finished"
      @update="updated"
    ></circular-count-down-timer>
  </div>
</template>

<script>
import Modal from "./Modal.vue";
import EndModal from "./EndModal.vue";

export default {
  name: "Shotvue",
  components: {
    Modal,
    EndModal,
  },
  data() {
    return {
      scoreVal: 0,
      limitScore: 25,
      x: 0,
      y: 0,
      large: 20,
      cross: true,
      timer: false,
      end: false,
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
      this.timer = !this.timer;
      this.cross = !this.cross;
    },
    facile: function () {
      this.large = 30;
    },
    normal: function () {
      this.large = 20;
    },
    expert: function () {
      this.large = 10;
    },
    finished: function () {
      console.log("finished");
      this.end = !this.end;
    },
    updated: function (status) {
      console.log(status.value); //{"value": 144, "seconds": 24, "minutes": 2, "hours": 0}
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
  border: 4px solid #ed7768;
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
  background-color: #ed7768;
}
</style>
