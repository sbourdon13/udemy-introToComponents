<template>
  <div class="col-xs-12 col-sm-6">
    <ul class="list-group">
      <app-server
        class="list-group-item"
        v-for="server in servers"
        :key="server.id"
        :server="server"
        @click.native="serverSelected(server)"
      ></app-server>
    </ul>
  </div>
</template>

<script>
import AppServer from "./Server.vue";
import { eventBus } from "../main";

export default {
  data() {
    return {
      servers: [
        {
          id: 1,
          status: "Normal"
        },
        {
          id: 2,
          status: "Critical"
        },
        {
          id: 3,
          status: "Unknown"
        },
        {
          id: 4,
          status: "Normal"
        }
      ]
    };
  },
  methods: {
    serverSelected(server) {
      // this method could be set in Server.vue instead
      eventBus.$emit("server-selected", server);
    }
  },
  components: {
    AppServer
  }
};
</script>

<style scoped>
</style>