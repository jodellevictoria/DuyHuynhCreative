<script setup lang="ts">
/**
 * TODO: Add Bio & experience
 * What can I provide
 */
</script>

<template>
  <div
    style="
      /* padding-top: 120px;
      padding-left: 50px;
      padding-right: 50px; */
      animation: fadeInAnimation ease 1s;
      animation-iteration-count: 1;
      animation-fill-mode: forwards;
    "
  >
    <!-- <video autoplay muted loop id="myVideo">
      <source
        src="https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/DemoReel.mp4?alt=media&token=5e322a23-a1a3-4b13-b1a6-3d6b6ed09a2d"
        type="video/mp4"
        style="max-height: 60%"
      />
    </video>

    <div
      style="
        position: absolute;
        background-color: black;
        opacity: 0.85;
        height: 100%;
        top: 0px;
        padding-top: 15%;
        padding-left: 10%;
        padding-right: 10%;
      "
    >
      <h2 style="font-family: Deuterium; font-weight: 500">About</h2>

      <div style="color: white; padding-left: 40px">
        <p>
          I’m a detail-oriented video production specialist and creative with years of experience in
          producing high-quality content for various clientele, from professional sports teams,
          weddings, to the travel aviation industry across the country.
        </p>
        <br />
        <p>
          Proficient in videography, editing, color correction, and providing clientele with high
          production value content, I excel in creating impactful and engaging storytelling that
          resonate with audiences from small to large scales. My diverse skill set and background
          enable me to approach projects with a nuanced and unique perspective, ensuring that each
          piece of content is both strategically aligned with client goals and visually compelling.
        </p>
        <br />
        <p>
          I am passionate about building strong relationships with clients and dedicated to
          delivering stories that provide a powerful voice and enhance brand presence.
        </p>
      </div>
    </div> -->

    <!-- The video -->
    <video autoplay muted loop class="myVideo">
      <source
        src="https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/DemoReel.mp4?alt=media&token=5e322a23-a1a3-4b13-b1a6-3d6b6ed09a2d"
        type="video/mp4"
      />
    </video>

    <!-- Optional: some overlay text to describe the video -->
    <div class="content">
      <h2 style="font-family: Deuterium; font-weight: 500">About</h2>

      <div style="color: white; padding: 25px">
        <p>
          I’m a detail-oriented video production specialist and creative with years of experience in
          producing high-quality content for various clientele, from professional sports teams,
          weddings, to the travel aviation industry across the country.
        </p>
        <br />
        <p>
          Proficient in videography, editing, color correction, and providing clientele with high
          production value content, I excel in creating impactful and engaging storytelling that
          resonate with audiences from small to large scales. My diverse skill set and background
          enable me to approach projects with a nuanced and unique perspective, ensuring that each
          piece of content is both strategically aligned with client goals and visually compelling.
        </p>
        <br />
        <p>
          I am passionate about building strong relationships with clients and dedicated to
          delivering stories that provide a powerful voice and enhance brand presence.
        </p>
      </div>
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

.myVideo {
  position: fixed;
  right: 0;
  bottom: 0;
  min-width: 100%;
  min-height: 100%;
}

/* Add some content at the bottom of the video/page */
.content {
  position: fixed;
  bottom: 0;
  background: black;
  opacity: 0.85;
  width: 100%;
  height: 100%;
  padding: 10%;
}
</style>
