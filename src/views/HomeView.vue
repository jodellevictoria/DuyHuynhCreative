<script setup lang="ts">
/**
 * TODO: Add Widget to turn on sound of Demo Reel
 * add video controls
 */
</script>

<template>
  <div>
    <div id="reel" ref="reel">
      <video autoplay muted loop id="myVideo">
        <source
          src="https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/DemoReel.mp4?alt=media&token=5e322a23-a1a3-4b13-b1a6-3d6b6ed09a2d"
          type="video/mp4"
        />
      </video>
    </div>
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
  animation: fadeInAnimation ease 4s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  z-index: 0;
  top: 64px;
  height: 100vh;
}

#myVideo {
  width: 100%;
}

h2 {
  color: white;
  font-size: 70px;
  font-weight: bold;
}
</style>
