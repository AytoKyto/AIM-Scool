<template>
  <div class="bigWrapper" v-if="cross">
    <div class="overlay"></div>
    <div class="wrapperModal">
      <div class="modal">
        <div class="header">
          <img class="logo" src="../assets/logo.svg" />
        </div>
        <p class="text">
          Bienvenue sur AIM TEST "Beta". <br />Cette application permet de vous
          d'entraîner et de tester votre shot. Pour cela vous devez cliquer le
          plus vite possible sur un cercle qui change de place pendant. Cela
          permettra d'évaluer et d'améliorer vos réflexes et votre précision.
          <br /><br />Vous avez 3 niveaux de difficulté, ils auront pour
          incidence de changer la taille du cercle.
        </p>
        <p><strong>Paramètres</strong></p>
        <label>Taille du cercle </label>
        <button
          @click="facile"
          :class="{ color: !toggleColor }"
          class="btn btn-primary"
          type="button"
        >
          Facile
        </button>
        <button @click="normal" class="btn btn-primary" type="button">
          Normal
        </button>
        <button @click="expert" class="btn btn-primary" type="button">
          Expert
        </button>
        <br />
        <br />
        <p>C'est partie pour 30 secondes</p>
        <button @click="crossF" class="btn btn-default">Start</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: ["cross", "crossF", "facile", "normal", "expert", "difficulty"],
  computed: {
    btn: function () {
      return {
        backgroundColor: "#70d3bf",
        color: "white",
      };
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.wrapperModal {
  position: fixed;
  left: 15vw;
  width: 70vw;
  padding: 2vw;
  z-index: 999;
  background-color: white;
  border-radius: 10px;
  color: black;
}
.overlay {
  background-image: url(../assets/blur.png);
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
<style>
.btn {
  border: 1px solid #70d3bf;
  color: #70d3bf;
  padding: 5px;
  border-radius: 1000000px;
  background-color: white;
  font-size: 1.2em;
  margin: 5px;
  width: 150px;
}
.btn-default {
  color: white;
  background-color: #70d3bf;
}

.btn:hover {
  color: white;
  background-color: #70d3bf;
}
.btn:focus {
  color: white;
  background-color: #70d3bf;
}
.btn-default:hover {
  color: #70d3bf;
  background-color: white;
}
.logo {
  width: 3.5vw;
  margin-right: 1vw;
}
.text {
  width: 40vw;
  margin: 0 auto;
  margin-top: 1vw;
  margin-bottom: 2.5vw;
}
</style>
