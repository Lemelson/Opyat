<template fluid>
  <v-card
    color="#edf2f7"
    flat
    tile
    height="80px"
  />
</template>

<script>

import Router from 'vue-router';

const router = new Router();

export default {
  name: 'Header',
  methods: {
    goBack() {
      router.go(-1);
    },
  },
};
</script>

<style scoped>
.header-logo {
  max-width: 120px;
}
</style>
