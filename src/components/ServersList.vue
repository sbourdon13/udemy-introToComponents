<template>
  <div class="col-xs-12 col-sm-6">
    <ul class="list-group">
      <app-server-status
        class="list-group-item"
        v-for="server in servers"
        :key="server.id"
        :data="server"
        @click.native="serverSelected(server)"
      ></app-server-status>
    </ul>
  </div>
</template>

<script>
import AppServerStatus from "./ServerStatus.vue";
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
    serverSelected(data) {
      eventBus.$emit("server-selected", data);
    }
  },
  components: {
    AppServerStatus
  }
};
</script>

<style scoped>
</style>