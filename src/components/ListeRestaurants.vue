<template>
  <div id="content">
    <table>
      <thead>
        <tr>
          <th>Nom</th>
          <th>Cuisine</th>
          <th>Action 1</th>
          <th>Action 2</th>
        </tr>
      </thead>
      <tbody>
        <Logo msg="Music? (YouTube)" />
        <!--nom -->
        <Restaurant n="Lorem ipsum ipsum lorem" c="lorem ipsum" />
        <!--cuisine-->
        <Restaurant n="Lorem ipsum ipsum lorem" c="lorem ipsum" />
        <!--modifier-->
        <Restaurant @click.native="modifer" n="Lorem ipsum ipsum lorem" c="lorem ipsum" />
        <!--supprimer-->
        <Restaurant @click.native="supprimer" n="Lorem ipsum ipsum lorem" c="lorem ipsum" />
      </tbody>
    </table>
    <Pagination />
  </div>
</template>

<script>
import Restaurant from "../components/Restaurant";
import Pagination from "../components/Pagination";
export default {
  components: { Restaurant, Pagination },
  methods: {
    supprimer() {
      //TODO
    },
    modifier() {
      //TODO
    }
  }
};
</script>

<style scoped>
#content {
  margin-top: 150px;
}

tr,
td {
  border: 1px solid black;
  border-collapse: collapse;
}

th {
  color: orangered;
  border: 1px solid black;
  border-collapse: collapse;
}
thead tr:hover {
  background-color: rgba(78, 78, 78, 0.726);
  padding: 5px;
  text-align: center;
}

table {
  margin-left: auto;
  margin-right: auto;
  border: 1px solid black;
  border-collapse: collapse;
}
</style>