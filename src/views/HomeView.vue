<script setup lang="ts">
/**
 * TODO: Add Widget to turn on sound of Demo Reel
 * add video controls
 */
</script>

<template>
  <div class="vignette" id="reel">
    <video autoplay muted loop id="myVideo">
      <source
        src="https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/DemoReel.mp4?alt=media&token=5e322a23-a1a3-4b13-b1a6-3d6b6ed09a2d"
        type="video/mp4"
      />
    </video>
  </div>
</template>

<style>
@keyframes fadeInAnimation {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
#reel {
  background-color: black;
  animation: fadeInAnimation ease 1s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  z-index: 0;
  top: 64px;
}

.vignette {
  box-shadow: inset 0 0 500px rgba(0, 0, 0, 0.4);
}

#myVideo {
  width: 100%;
}
</style>
