<script setup lang="ts">
const model = defineModel({ default: { title: '', link: '', roles: [] } })
</script>

<template>
  <div class="background">
    <h2>{{ model.title }}</h2>
    <video>
      <source :src="model.link" type="video/mp4" />
    </video>
  </div>
</template>

<style>
.background {
  position: fixed; /* Stay in place front is invalid - may break your css so removed */

  z-index: 5;
  height: 100%;
  width: 100%;
  opacity: 0.7;
  background-color: black;
}
</style>
