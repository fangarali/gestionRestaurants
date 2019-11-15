<template>
  <img id="animation" alt="Chef buffa" src="../assets/img/bufchef.png" />
</template>

<script>
export default {
  name: "Logo"
};
</script>

<style scoped>
#animation {
  animation: rotation 10s infinite linear;
}

img {
  display: block;
  height: 100px;
}

@keyframes rotation {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(359deg);
  }
}
</style>