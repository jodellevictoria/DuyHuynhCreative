<script setup lang="ts">
import { RouterView } from 'vue-router'
import Nav from '@/components/Nav.vue'
</script>

<template>
  <v-app>
    <Nav />
  </v-app>
  <RouterView style="margin-top: 70px" />
</template>

<style scoped>
v-app {
  display: flex;
  flex-direction: column;
}
</style>
