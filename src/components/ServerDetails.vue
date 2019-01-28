<template>
  <div class="col-xs-12 col-sm-6">
    <strong>Server Details</strong>
    <template v-if="data.id">
      <p>ID: {{ data.id }}</p>
      <p>Status: {{ data.status }}</p>
      <button @click="changeStatus">Change status</button>
    </template>
    <template v-else>
      <p>No server selected</p>
    </template>
  </div>
</template>

<script>
import { eventBus } from "../main";
export default {
  data() {
    return {
      data: {
        id: null,
        status: null
      }
    };
  },
  methods: {
    changeStatus() {
      this.data.status = "Updated";
      eventBus.$emit("change-status", this.data);
    }
  },
  created() {
    eventBus.$on("server-selected", data => {
      Object.assign(this.data, data);
    });
  }
};
</script>

<style scoped>
</style>