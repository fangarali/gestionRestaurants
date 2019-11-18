<template>
  <div id="content">
    <h1>Liste des {{ nbRestaurants }} restaurants</h1>
    <h3>{{ message }}</h3>
    <FormRestaurant @ajout="ajouterResto" />
    <p>
      Filtrer par nom :
      <input type="text" v-model="nomRecherche" v-on:input="filtrerParNom()" />
    </p>
    <p>
      Page à afficher : &laquo;
      <input
        type="range"
        min="5"
        max="100"
        v-model="pagesize"
        v-on:input="changePageSize()"
      />
      &raquo;
    </p>
    {{ pageCourante }}
    <button @click="pagePrec" v-bind:disabled="pageCourante == 0">
      &laquo;
    </button>
    {{ pagesize }}
    <button @click="pageSuiv" v-bind:disabled="pageCourante == nbPagesTotal">
      &raquo;
    </button>
    {{ nbPagesTotal }}
    <table>
      <thead></thead>
      <thead>
        <tr>
          <th>Nom</th>
          <th>Cuisine</th>
          <th>Action</th>
        </tr>
      </thead>

      <Restaurant
        v-for="(r, index) in restaurants"
        :key="index"
        :n="r.name"
        :c="r.cuisine"
        :id="r._id"
        @supprimer="suprimerResto"
      />
    </table>
    <br />
    <br />
    <br />
    <br />
    <br />
  </div>
</template>

<script>
import Restaurant from "../components/Restaurant";
import FormRestaurant from "../components/FormRestaurant";

export default {
  components: { Restaurant, FormRestaurant },
  data: () => {
    return {
      nom: "",
      cuisine: "",
      nvNom: "",
      nvCuisine: "",
      restaurants: [],
      pageCourante: 0,
      nomRecherche: "",
      pagesize: 5,
      nbPagesTotal: 0,
      nbRestaurants: 0,
      message: ""
    };
  },
  mounted() {
    this.getResto();
  },
  methods: {
    getResto() {
      let url =
        "http://localhost:8089/api/restaurants?page=" +
        this.pageCourante +
        "&pagesize=" +
        this.pagesize +
        "&name=" +
        this.nomRecherche;
      fetch(url)
        .then(response => {
          return response.json();
        })
        .then(responseJS => {
          this.restaurants = responseJS.data;
          this.nbRestaurants = responseJS.count;
          this.nbPagesTotal = Math.ceil(this.nbRestaurants / this.pagesize);
        });
    },
    actionAfaire(obj) {
      console.log(obj);
      switch (obj.msg) {
        case "ajouter":
          this.ajouterResto(obj);
          break;
        case "supprimer":
          this.suprimerResto(obj.id);
      }
    },
    ajouterResto(resto) {
      let data = new FormData();
      data.append("nom", resto.nom);
      data.append("cuisine", resto.cuisine);

      let url = "http://localhost:8089/api/restaurants";
      fetch(url, {
        method: "POST",
        body: data
      })
        .then(response => {
          return response.json();
        })
        .then(responseJS => {
          console.log(responseJS.msg);
          this.nbRestaurants++;
          this.message =
            "Restaurant n°" + responseJS.result + " inséré avec succès !";
          setTimeout(() => {
            this.message = "";
          }, 3000);
        });
    },
    suprimerResto(id) {
      const msg = "Voulez-vous vraiment supprimer le restaurant n°" + id + "?";
      if (confirm(msg)) {
        let url = "http://localhost:8089/api/restaurants/" + id;
        fetch(url, {
          method: "DELETE"
        })
          .then(response => {
            return response.json();
          })
          .then(responseJS => {
            console.log(responseJS);
            this.getResto();
            this.message = "Restaurant avec id = " + id + " supprimé !";
            setTimeout(() => {
              this.message = "";
            }, 3000);
          });
      }
    },
    filtrerParNom() {
      this.getResto();
    },
    changePageSize() {
      this.getResto();
    },
    pageSuiv() {
      this.pageCourante++;
      this.getResto();
    },
    pagePrec() {
      this.pageCourante--;
      this.getResto();
    }
  }
};
</script>

<style scoped>
#content {
  margin-top: 150px;
}

tr,
td {
  border: 1px solid black;
  border-collapse: collapse;
}

th {
  color: orangered;
  border: 1px solid black;
  border-collapse: collapse;
}
thead tr:hover {
  background-color: rgba(78, 78, 78, 0.726);
  padding: 5px;
  text-align: center;
}

table {
  margin-left: auto;
  margin-right: auto;

  border: 2px solid orangered;
  border-radius: 3px;
}
</style>
