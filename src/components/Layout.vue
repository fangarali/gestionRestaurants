<template>
  <div>
    <AppHeader />
    <table>
      <tr>
        <Restaurant nom="pepe" cuisine="popo" />
        <Restaurant nom="pepe" cuisine="popo" />
      </tr>
    </table>
    <AppFooter />
  </div>
</template>

<script>
import AppHeader from "./AppHeader";
import Restaurant from "./Restaurant";
import AppFooter from "./AppFooter";
export default {
  components: { AppHeader, Restaurant, AppFooter }
};
</script>

<style scoped></style>
