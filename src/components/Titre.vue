<template>
  <h2>{{msg}}</h2>
</template>

<script>
export default {
  name: "titre",
  props: {
    msg: String
  }
};
</script>

<style scoped>
@font-face {
  font-family: "Cookie";
  src: url("../assets/fonts/Cookie.ttf");
}
h2 {
  font-family: "Cookie";
  color: white;
}
</style>