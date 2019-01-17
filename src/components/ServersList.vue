<template>
  <div class="col-xs-12 col-sm-6">
    <ul class="list-group">
      <app-server-status class="list-group-item" v-for="index in 5" :key="index" :index="index"></app-server-status>
    </ul>
  </div>
</template>

<script>
import AppServerStatus from "./ServerStatus.vue";
export default {
  components: {
    AppServerStatus
  }
};
</script>

<style scoped>
div {
  border: 1px solid blue;
}
</style>