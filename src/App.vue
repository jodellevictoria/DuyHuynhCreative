<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router';
import Nav from '@/components/Nav.vue';
</script>

<template>
  <v-app>
    <Nav />
  </v-app>
  <RouterView />
</template>

<style scoped>
v-app{
  display:flex;
  flex-direction: column;
}
</style>