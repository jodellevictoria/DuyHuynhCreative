<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router';
import Nav from ""

components:{
  Nav,
}
</script>

<template>
  <v-app>
    <Nav />
  </v-app>
  <RouterView />
</template>

<style scoped>
nav {
  width: 100%;
  font-size: 12px;
  top:0px;
}
</style>
