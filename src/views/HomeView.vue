<script setup lang="ts">
import { ref } from 'vue'

const videoRef = ref<HTMLVideoElement | null>(null)
const isMuted = ref(true)
const isLoading = ref(true) // Add a ref to track loading state

const toggleSound = () => {
  if (videoRef.value) {
    isMuted.value = !isMuted.value
    videoRef.value.muted = isMuted.value
  }
}

// Update the isLoading ref when the video metadata is loaded
const onLoadedData = () => {
  isLoading.value = false
}
</script>

<template>
  <div>
    <div class="spinner"></div>
    <div id="reel" ref="reel">
      <video autoplay muted loop id="myVideo" ref="videoRef" @loadeddata="onLoadedData">
        <source
          src="https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/DemoReel.mp4?alt=media&token=5e322a23-a1a3-4b13-b1a6-3d6b6ed09a2d"
          type="video/mp4"
        />
      </video>
      <button @click="toggleSound" class="sound-toggle">
        <div v-if="!isMuted">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            height="24px"
            viewBox="0 -960 960 960"
            width="24px"
            fill="#FFFFFF"
          >
            <path
              d="M280-360v-240h160l200-200v640L440-360H280Zm80-80h114l86 86v-252l-86 86H360v80Zm100-40Z"
            />
          </svg>
        </div>
        <div v-else>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            height="24px"
            viewBox="0 -960 960 960"
            width="24px"
            fill="#FFFFFF"
          >
            <path
              d="M560-131v-82q90-26 145-100t55-168q0-94-55-168T560-749v-82q124 28 202 125.5T840-481q0 127-78 224.5T560-131ZM120-360v-240h160l200-200v640L280-360H120Zm440 40v-322q47 22 73.5 66t26.5 96q0 51-26.5 94.5T560-320ZM400-606l-86 86H200v80h114l86 86v-252ZM300-480Z"
            />
          </svg>
        </div>
      </button>
      <div class="bio">
        <h2>Duy Huynh Creative</h2>
        <br />
        <p>
          I’m a detail-oriented video production specialist and creative with years of experience in
          producing high-quality content for various clientele, from professional sports teams,
          weddings, to the travel aviation industry across the country.
        </p>
        <p>
          Proficient in videography, editing, color correction, and providing clientele with high
          production value content, I excel in creating impactful and engaging storytelling that
          resonate with audiences from small to large scales. My diverse skill set and background
          enable me to approach projects with a nuanced and unique perspective, ensuring that each
          piece of content is both strategically aligned with client goals and visually compelling.
        </p>
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

.sound-toggle {
  position: absolute;
  bottom: 20px;
  right: 20px;
  background-color: rgba(0, 0, 0, 0.8);
  border: none;
  padding: 10px;
  font-size: 24px;
  cursor: pointer;
  z-index: 10;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.material-symbols-outlined {
  font-variation-settings:
    'FILL' 0,
    'wght' 400,
    'GRAD' 0,
    'opsz' 48;
}

#reel {
  background-color: black;
  animation: fadeInAnimation ease 2s;
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

.bio {
  display: none;
}

.spinner {
  border: 8px solid rgba(0, 0, 0, 0.1); /* Light grey background */
  border-left: 8px solid #3498db; /* Blue foreground */
  border-radius: 50%;
  width: 50px;
  height: 50px;
  animation: spin 1s linear infinite;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}

@media (max-width: 768px) {
  .bio {
    display: block;
    color: white;
    padding: 25px;
  }
  h2 {
    color: white;
    font-size: 30px;
    text-align: center;
  }
}
</style>
