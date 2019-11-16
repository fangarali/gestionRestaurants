<template>
  <div id="app">
    <Layout />
  </div>
</template>

<script>
/*
 Reprendre l'exemple des restaurants et le faire marcher dans un projet compilé, avec fichiers .vue etc.
 Vous regarderez le premier tutorial sur les "expenses", mais n'utiliserez pas Firecloud.
 A la place vous devrez ajouter des requêtes fetch dans un composant ListeRestaurant qui sera ajouté dans 
 le template de App.vue. 
 Faites un affichage des restaurants avec pagination, réglage du nombre de restaurants affichés, 
 affichage du nombre de restaurants. 
                  
 Optionnel : essayer d'utiliser un composant custom <Restaurant> pour l'affichage d'un restaurant,
 Optionnel : ajouter un formulaire et coder l'ajout d'un restaurant. Vous pourrez  metttre le code HTML dans le composant ListeRestaurants,
 Optionnel : utiliser à la place un composant <FormRestaurant> pour gérer l'ajout. Rappelez-vous comment on avait fait pour communiquer avec un event custom entre deux composants...
 Optionnel : idem pour suppression (icone dans le tableau à droite, dans la liste), et modification
*/
import Layout from "./components/Layout";
export default {
  name: "app",
  components: { Layout }
};
</script>

<style >
html,
body {
  height: 100%;

  background: gainsboro;
}

body {
  display: flex;
  flex-direction: column;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
