<template>
  <div>Server #{{ data.id }}</div>
</template>

<script>
import { eventBus } from "../main";

export default {
  props: {
    data: Object
  },
  created() {
    eventBus.$on("change-status", data => {
      if (this.data.id === data.id) {
        this.data.status = data.status;
      }
    });
  }
};
</script>

<style scoped>
</style>