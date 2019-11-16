<template>
  <div id="restaurant">
    <td>{{nom}}</td>
    <td>{{cuisine}}</td>
    <td>
      <span>
        <img src="../assets/src/img/corbeille.png" />
      </span>
    </td>
  </div>
</template>

<script>
export default {
  name: "restaurant",
  props: [nom, cuisine]
};
</script>

<style scoped>
#restaurant {
  margin-top: 150px;
}

td {
  padding: 5px;
}

table,
tr,
td {
  border: 1px solid black;
  border-collapse: collapse;
}

tr:hover {
  background-color: lightGrey;
  padding: 5px;
}
</style>