<template>
  <div class="pagination">
    <a href="#">&laquo;</a>
    <a href="#">1</a>
    <a href="#" class="active">2</a>
    <a href="#">3</a>
    <a href="#">...</a>
    <a href="#">4</a>
    <a href="#">5</a>
    <a href="#">6</a>
    <a class="prec" href="#">&raquo;</a>
  </div>
</template>


<script>
export default {};
</script>

<style scoped>
.pagination {
  display: inline-block;
}

.pagination a {
  color: orangered;
  float: left;
  padding: 8px 16px;
  font-size: 1rem;
  font-weight: bold;
  text-decoration: none;
  transition: background-color 0.3s;
  border: 1px solid #ddd;
}

.pagination a:hover {
  background-color: grey;
  border-radius: 5px;
}
</style>