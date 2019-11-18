<template>
  <div class="form-restaurant">
    <label> Nom : <input type="text" v-model="nomResto" /> </label>
    <label> Cuisine : <input type="text" v-model="cuisineResto" /> </label>

    <span @click="ajouterResto">
      <img src="../assets/img/ajouter.png" />
    </span>

    <br />
    <br />
  </div>
</template>

<script>
export default {
  name: "form-restaurant",
  data: () => {
    return {
      nomResto: "",
      cuisineResto: ""
    };
  },
  methods: {
    ajouterResto() {
      if (this.nomResto !== "" && this.cuisineResto !== "") {
        const resto = {
          nom: this.nomResto,
          cuisine: this.cuisineResto
        };
        this.nomResto = "";
        this.cuisineResto = "";
        this.$emit("ajout", resto);
      } else {
        alert("Champ(s) Manquant(s) !");
      }
    }
  }
};
</script>

<style scoped>
input {
  border: 2px solid orangered;
  border-radius: 4px;
}
#form-restaurant {
  margin-top: -20px;
}
span {
  margin-left: 20px;
  margin-top: 10px;
  cursor: pointer;
  /* padding: 10px; */
}
img {
  max-height: 100%;
  max-width: 100%;
}
</style>
