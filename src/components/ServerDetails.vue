<template>
  <div class="col-xs-12 col-sm-6">
    <strong>Server Details</strong>
    <template v-if="server">
      <p>ID: {{ server.id }}</p>
      <p>Status: {{ server.status }}</p>
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
      server: null
    };
  },
  methods: {
    changeStatus() {
      this.server.status = "Updated";
      // no need for event bus since we're aready pointing to the initial server object
    }
  },
  created() {
    eventBus.$on("server-selected", server => {
      // Object.assign(this.server, server);
      this.server = server;
      //=> if we set up the server object this way,
      // it's a copy of the pointer to the unique place in memory
      // of our initial object in ServersList.vue, because an object
      //is a reference type
    });
  }
};
</script>

<style scoped>
</style>