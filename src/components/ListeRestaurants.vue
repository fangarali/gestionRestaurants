<template>
  <div id="content">
    <table>
      <tbody>
        <Restaurant n="pepe" c="popo" />
        <Restaurant n="pepe" c="popo" />
        <Restaurant n="pepe" c="popo" />
        <Restaurant n="pepe" c="popo" />
      </tbody>
    </table>
  </div>
</template>

<script>
import Restaurant from "../components/Restaurant";
export default {
  components: { Restaurant }
};
</script>

<style scoped>
#content {
  margin-top: 150px;
}

table {
  margin-left: auto;
  margin-right: auto;
  border: 1px solid black;
  border-collapse: collapse;
}
</style>