<template>
  <div class="container">
    <app-header></app-header>
    <app-servers></app-servers>
    <app-footer></app-footer>
  </div>
</template>

<script>
import AppHeader from "./components/Header.vue";
import AppServers from "./components/ServersList.vue";
import AppFooter from "./components/Footer.vue";

export default {
  data() {
    return {};
  },
  components: {
    AppHeader,
    AppServers,
    AppFooter
  }
};
</script>

<style>
</style>
