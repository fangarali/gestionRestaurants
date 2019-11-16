<template>
  <div id="sticky-header">
    <div id="box-left">
      <Logo msg="Citation ?" @click.native="randomQuote" />
      <span class="fleche">
        <img src="../assets/img/fleche.png" />
      </span>
    </div>
    <div id="box-center">
      <Titre :msg="citation" />
    </div>
    <div id="box-right">
      <Logo @click.native="randomMusic" msg="Music? (YouTube)" />
    </div>
  </div>
</template>

<script>
import Logo from "./Logo";
import Titre from "./Titre";
import getRandomInt from "../js/myFunctions";
export default {
  name: "AppHeader",
  data: () => {
    return {
      citation: "",
      citations: [
        '"Ici, prendre son temps est le meilleur moyen de n\'en pas perdre."',
        '"Le meilleur usage que l\'on puisse faire de la parole est de se taire."',
        '"Tu mets du désordre. Et le désordre est le meilleur serviteur de l\'ordre établi."',
        '"L\'hypothèse est chose fragile, Le fait est un meilleur soutien."',
        '"L’on est plus sociable et d’un meilleur commerce par le cœur que par l’esprit."',
        '"La vie est un restaurant petit, mauvais et cher. En plus, c\'est trop court."'
      ],
      musicYoutube: ["0iOKsCDxy-Y", "sp4-U53qeMc", "J1H2_VTGtk0", "mGsFF5jtNE8"]
    };
  },
  methods: {
    randomQuote() {
      this.citation = this.citations[getRandomInt(this.citations.length - 1)];
    },
    randomMusic() {
      window.open(
        "https://www.youtube.com/watch?v=".concat(
          this.musicYoutube[getRandomInt(this.musicYoutube.length - 1)]
        ),
        "_blank"
      );
    }
  },
  mounted() {
    this.randomQuote();
  },
  components: {
    Logo,
    Titre
  }
};
</script>

<style scoped>
#box-left {
  float: left;
  width: 10%;
  margin-left: 3rem;
  /*border: 1px solid black;*/
}

#box-left .fleche {
  /* Position the tooltip */
  visibility: hidden;
  position: absolute;
  z-index: -1;
  margin-left: 16rem;
  margin-top: -1.5rem;
}
#box-left:hover .fleche {
  visibility: visible;
}

#box-center {
  float: left;
  width: 50%;
  margin-top: 1rem;
  font-size: 100%;
  margin-left: 6rem;
  /*border: 1px solid black;*/
}

#box-right {
  float: right;
  margin-right: 4rem;
  width: 10%;
  /*border: 1px solid black;*/
}

#sticky-header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 16.5px;
  background-color: gray;
  border-bottom: solid 2px lightsalmon;
}
</style>
