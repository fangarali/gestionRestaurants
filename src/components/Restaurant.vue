<template>
  <tr>
    <td>
      <h2>{{n}}</h2>
    </td>
    <td>
      <h2>{{c}}</h2>
    </td>
    <td>
      <h2>
        <span>
          <img src="../src/assets/img/corbeille.png" />
        </span>
      </h2>
    </td>
    <td>
      <h2>{{c}}</h2>
    </td>
  </tr>
</template>

<script>
export default {
  name: "restaurant",
  props: ["n", "c"]
};
</script>

<style scoped>
table,
tr,
td {
  border: 1px solid black;
  border-collapse: collapse;
}

tr:hover {
  background-color: rgba(255, 68, 0, 0.726);
  padding: 5px;
}

td {
  padding: 5px;
}
</style>