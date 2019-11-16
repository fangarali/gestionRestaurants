<template>
  <div id="logo">
    <img id="animation" alt="Chef buffa" src="../assets/img/bufchef.png" />
    <span class="info">{{ msg }}</span>
  </div>
</template>

<script>
export default {
  name: "Logo",
  props: ["msg"]
};
</script>

<style scoped>
#logo {
  cursor: pointer;
}

#logo .info {
  visibility: hidden;
  width: 120px;
  background-color: rgba(94, 94, 94, 0.815);
  color: #fff;
  font-family: "Courier New", "Courier", "monospace";
  text-align: center;
  border-radius: 6px;
  padding: 5px 0;
  position: absolute;
  z-index: 1;
  margin-left: -70px;
  margin-top: 1.15rem;
}

#logo:hover .info {
  visibility: visible;
}

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
