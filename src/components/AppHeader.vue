<template>
  <div id="sticky-header">
    <div id="box-left">
      <Logo />
    </div>
    <div id="box-right">
      <Logo />
    </div>
  </div>
</template>

<script>
import Logo from "./components/Logo";
export default {
  name: AppHeader,
  components: {
    Logo
  }
};
</script>

<style scoped>
#box-left {
  float: left;
}

#box-right {
  float: right;
  margin-right: 2rem;
}

.sticky-header {
  position: fixed;
  top: 0;
  left: 0;
  padding: 16.5px;
  width: 100%;
  background-color: gray;
  border-bottom: solid 2px lightsalmon;
}
</style>
