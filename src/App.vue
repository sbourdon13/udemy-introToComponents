<template>
  <div class="container">
    <app-header></app-header>
    <hr>
    <div class="row">
      <app-servers></app-servers>
      <app-server-details></app-server-details>
    </div>
    <hr>
    <app-footer></app-footer>
  </div>
</template>

<script>
import AppHeader from "./components/Header.vue";
import AppServers from "./components/ServersList.vue";
import AppServerDetails from "./components/ServerDetails.vue";
import AppFooter from "./components/Footer.vue";

export default {
  data() {
    return {};
  },
  components: {
    AppHeader,
    AppServers,
    AppServerDetails,
    AppFooter
  }
};
</script>

<style>
</style>
