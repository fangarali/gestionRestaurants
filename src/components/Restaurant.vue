<template>
  <tr>
    <td>
      <h2 v-show="n">{{ n }}</h2>
    </td>
    <td>
      <h2 v-show="c">{{ c }}</h2>
    </td>
    <td>
      <h2>
        <span @click="supResto">
          <img src="../assets/img/corbeille.png" />
        </span>
      </h2>
    </td>
  </tr>
</template>

<script>
export default {
  props: ["n", "c", "id"], //nom, cuisine, id
  methods: {
    modifResto() {
      alert("hello");
    },
    supResto() {
      this.$emit("supprimer", this.id);
    }
  },
  data() {
    return {};
  }
};
</script>

<style scoped>
tr,
td {
  border: 1px solid black;
  font-size: 10px;
  border-collapse: collapse;
}

span {
  cursor: pointer;
}

tr:hover {
  background-color: rgba(255, 68, 0, 0.726);
  padding: 5px;
}

td {
  padding: 5px;
}
</style>
