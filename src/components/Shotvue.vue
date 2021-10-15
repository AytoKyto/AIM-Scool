<template>
  <div class="wrapper">
    <div class="containerData">
      <div class="dataWrapper">
        <p class="score">
          <span class="color">{{ scoreVal }}</span
          ><br />HIT
        </p>
      </div>
      <div class="dataWrapper">
        <p class="score">
          <span class="color">{{ clickVal }}</span
          ><br />CLICK
        </p>
      </div>
      <div class="diffWrapper">
        <p class="score">
          <span class="color">{{ difficulty }}</span
          ><br />DIFFICULE
        </p>
      </div>
      <div class="chronoWrapper">
        <circular-count-down-timer
          v-if="timer"
          :initial-value="30"
          :steps="30"
          :size="80"
          @finish="finished"
        ></circular-count-down-timer>
      </div>
      <div class="nameWrapper"></div>
    </div>
    <Modal
      :difficulty="difficulty"
      :cross="cross"
      :crossF="crossF"
      :facile="facile"
      :normal="normal"
      :expert="expert"
    />
    <EndModal
      :end="end"
      :scoreVal="scoreVal"
      :clickVal="clickVal"
      :difficulty="difficulty"
    />
    <div class="shotWrapper" @click="clickF">
      <div :style="styleCirlce" @click="changeDirection" class="circle"></div>
    </div>
  </div>
</template>

<script>
import Modal from "./Modal.vue";
import EndModal from "./EndModal.vue";
import { gsap } from "gsap";

export default {
  name: "Shotvue",
  components: {
    Modal,
    EndModal,
  },
  data() {
    return {
      difficulty: "Normal",
      scoreVal: 0,
      clickVal: 0,
      limitScore: 999999,
      x: 0,
      y: 0,
      large: 20,
      cross: true,
      timer: false,
      end: false,
      truc: this,
    };
  },
  methods: {
    logic: function () {
      this.scoreVal++;
      if (this.scoreVal < this.limitScore) {
        this.x = Math.random() * 95;
        this.y = Math.random() * 75;
      } else {
        alert("error");
      }
    },
    changeDirection: function () {
      console.log(this.scoreVal);
      gsap.fromTo(".circle", { scale: 0, duration:0.3},{ scale: 1, duration:0.3, onComplete: this.logic() });
    },
    crossF: function () {
      this.timer = !this.timer;
      this.cross = !this.cross;
    },
    clickF: function () {
      this.clickVal++;
    },
    facile: function () {
      this.large = 30;
      this.difficulty = "Facile";
    },
    normal: function () {
      this.large = 20;
      this.difficulty = "Normal";
    },
    expert: function () {
      this.large = 10;
      this.difficulty = "Expert";
    },
    finished: function () {
      console.log("finished");
      this.end = !this.end;
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
  border: 1px solid white;
  height: 80vh;
  margin: 1vw;
  background-color: #0a17172a;
  cursor: cell;
  margin-bottom: 5vh;
}
.circle {
  border-radius: 1000000px;
  background-color: #70d3bf;
}
.containerData {
  display: flex;
  justify-content: center;
}
.containerData {
  border: 1px solid white;
  margin: 1vw;
  display: flex;
  justify-content: left;
  height: 5vw;
}
.dataWrapper {
  border-left: 1px solid white;
  border-right: 1px solid white;
  width: 5vw;
}
.diffWrapper {
  border-right: 1px solid white;
  width: 10vw;
}
.chronoWrapper {
  border-right: 1px solid white;
  width: 56vw;
}
.color {
  font-size: 1.5em;
  color: #70d3bf;
  font-weight: bold;
  text-transform: uppercase;
}
.score {
  color: white;
}
</style>
