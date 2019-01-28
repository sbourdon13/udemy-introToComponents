<template>
  <li style="cursor: pointer">Server #{{ server.id }}</li>
</template>

<script>
export default {
  props: {
    server: Object
  }
};
</script>

<style scoped>
</style>