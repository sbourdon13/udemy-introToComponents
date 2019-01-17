<template>
  <div class="col-xs-12 col-sm-6">
    <ul class="list-group">
      <li
        is="app-server-status"
        class="list-group-item"
        v-for="index in 5"
        :key="index"
        :index="index"
      ></li>
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
</style>