<script setup lang="ts">
</script>

<template>
  <div class="vignette" id="reel">
    <video autoplay muted loop id="myVideo">
      <source src="/src/assets/240619-2024 Demo_Reel v2.mp4" type="video/mp4">
    </video>
  </div>
</template>

<style>
  #reel{
    z-index: 0;
    top:64px;
  }

  .vignette{
    box-shadow: inset 0 0 500px rgba(0, 0, 0, 0.4);
  }

  #myVideo {
    width: 100%;
  }
</style>
