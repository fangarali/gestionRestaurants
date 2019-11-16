<template>
  <div id="layout">
    <AppHeader />
    <ListeRestaurants />
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from "./AppHeader";
import ListeRestaurants from "./ListeRestaurants";
import AppFooter from "./AppFooter";
export default {
  name: "layout",
  components: { AppHeader, ListeRestaurants, AppFooter }
};
</script>

<style scoped>
</style>
