<template>
  <div>
    <div v-if="modal_active == true">
      <div
        style="
          background-color: black;
          top: 0px;
          height: 120vh;
          width: 120vw;
          opacity: 0.7;
          z-index: 3;
          position: fixed;
          backdrop-filter: blur(20px);
        "
        @click="stop_watching"
      ></div>
      <video id="videoplayer" ref="videoplayer" controls autoplay class="video_player">
        <source :src="video_in_modal.link" type="video/mp4" />
      </video>
      <!-- <video muted autoplay class="vid_player">
        <source :src="video_in_modal.link" type="video/mp4" />
      </video> -->
    </div>
    <div class="projects">
      <h2 class="type_title">Sports</h2>

      <div class="videos">
        <div
          v-for="(video, index) in sports_videos"
          v-bind:key="index"
          class="video"
          @click="watch_video(video)"
        >
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()">
            <source :src="video.link + '#t=10,50'" type="video/mp4" /></video
          ><br />
          <!-- <img style="max-width: 650px" :src="`src/assets${video.src}`" /> -->
          <span class="project_title">{{ video.name }}</span>
        </div>
      </div>

      <h2 class="type_title">Products</h2>
      <div class="videos">
        <div
          v-for="(video, index) in product_videos"
          v-bind:key="index"
          class="video"
          @click="watch_video(video)"
        >
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()">
            <source :src="video.link + '#t=10,50'" type="video/mp4" /></video
          ><br />
          <!-- <img style="max-width: 650px" :src="`src/assets${video.src}`" /> -->
          <span class="project_title">{{ video.name }}</span>
        </div>
      </div>

      <h2 class="type_title">Brand Content</h2>
      <div class="videos">
        <div
          v-for="(video, index) in branding_videos"
          v-bind:key="index"
          class="video"
          @click="watch_video(video)"
        >
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()">
            <source :src="video.link + '#t=10,50'" type="video/mp4" /></video
          ><br />
          <!-- <img style="max-width: 650px" :src="`src/assets${video.src}`" /> -->
          <span class="project_title">{{ video.name }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
/**
 *
 * TODO: Start Mobile
 */

import { nextTick, ref, watch } from 'vue'

let video_in_modal = ref({ name: '', link: '', roles: [] })
let modal_active = ref(false)
// const videoplayer = ref<HTMLVideoElement | null>(null)

function stop_watching() {
  console.log('instopwatch')
  // if (videoplayer.value) {
  //   videoplayer.value.pause()
  //   videoplayer.value.currentTime = 0
  // }
  modal_active.value = false

  console.log(modal_active)
}

function watch_video(video: any) {
  video_in_modal.value = video
  modal_active.value = true
  // nextTick(() => {
  //   if (videoplayer.value) {
  //     videoplayer.value.play()
  //   }
  // })
}

// watch(modal_active, (newVal) => {
//   if (newVal && videoplayer.value) {
//     videoplayer.value.play()
//   }
// })
const sports_videos = [
  {
    name: 'TFC Jonathan Osorio Contract Extension',
    src: '/Sports/OsorioSigning.png',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/sports%2F180829-MLS-FEA-OSO%20RE-SIGN%20v3%20(2020_09_29%2000_42_32%20UTC).mp4?alt=media&token=a948555a-854c-4512-ad8b-5aa7987c8870',
    roles: ['', '']
  },
  {
    name: 'Toronto Arrows',
    src: '/Sports/Arrows.png',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/sports%2F220516-TORvsDAL%20Narrative%20Spot.mp4?alt=media&token=cb729d4e-bbc0-4c78-af9b-674d86f83485',
    roles: ['', '']
  },
  {
    name: 'Toronto Raptors Tailgate',
    src: '/Sports/RapsTailgate.png',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/sports%2FNBA-TWT-190520-RAPTORS%20TAILGATE.mp4?alt=media&token=d94a340c-6dcd-4ac8-9bed-800310c45a50',
    roles: ['', '']
  },
  {
    name: 'CCYAA Celebrity Classic 2023',
    src: '/Sports/CCYAA2023.png',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/sports%2F240606%20-%20CCYAA_CC_Hilites.mp4?alt=media&token=adbc3a20-6467-4573-a7c8-1db83d08b44a',
    roles: ['', '']
  }
]

const product_videos = [
  {
    name: 'Sapporo Spot',
    src: '/Product/Sapporo.png',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/product%2F1080_30s_Sapporo%20Spot%20v2.mp4?alt=media&token=f5f14096-1cce-4585-9715-82daeb4dfd38',
    roles: ['', '']
  },
  {
    name: 'Whiskey Spot',
    src: '/Product/Whiskey.png',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/product%2F1080_30s_Whiskey%20Spot.mp4?alt=media&token=674529ca-e225-441b-9ab7-e4a2f1d20b93',
    roles: ['', '']
  },
  {
    name: 'Knurling Dental',
    src: '/Product/knurling.png',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/product%2F200507-KNU-WEB-Free%20Shipping%2030%20SEC%20Spot%20B%20TITLE.mp4?alt=media&token=cbd34609-9750-43e5-95b2-649ddf7a23b7',
    roles: ['', '']
  },
  {
    name: 'Air Canada - Summer Travel Drinks',
    src: '/Sports/CCYAA2023.png',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/product%2F230720-16x9%20Summer%20Travel%20Drinks%20v10%20EN.mp4?alt=media&token=62def7be-2f95-4f8f-9a53-3dee9e3eda9c',
    roles: ['', '']
  }
]

const branding_videos = [
  {
    name: 'Air Canada Free Wifi',
    src: '/Sports/CCYAA2023.png',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/branding%2F230725-EN169-Free%20Wifi%20Concept%20v5%20ONB.mp4?alt=media&token=410bac4a-2839-43b8-9c58-2b360959ad75',
    roles: ['', '']
  },
  {
    name: "Air Canada X Disney & Pixar's film, Turning Red",
    src: '/Sports/CCYAA2023.png',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/branding%2FAir%20Canada%20Celebrating%20Disney%20and%20Pixar%E2%80%99s%20new%20film%2C%20Turning%20Red.mp4?alt=media&token=6954555f-864a-4fb2-888c-473a277fa152',
    roles: ['', '']
  },
  {
    name: 'Air Canada: To the next generation in aviation',
    src: '/Sports/CCYAA2023.png',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/branding%2F230328-Rosemary%20Flight%20Sim%20S%2BD%20v3.mp4?alt=media&token=92854419-b44a-4dcb-9ad6-4a500c50f0e5',
    roles: ['', '']
  },
  {
    name: "Air Canada: Zoey's Story",
    src: '/Sports/CCYAA2023.png',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/branding%2F231107-Zoeys%20Story%20v15.2%20EN.mp4?alt=media&token=5d0a6167-7cc0-4534-8fdb-3c6081a79c63',
    roles: ['', '']
  },
  {
    name: 'Air Canada Black History Month',
    src: '/Sports/CCYAA2023.png',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/branding%2FTEAS-BHM%201st%20Piece%20v6%20EN.mp4?alt=media&token=d6e89776-d66b-4a45-88c8-5e35f2b45dd5',
    roles: ['', '']
  }
]
</script>

<style>
/* Global Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html,
body {
  width: 100%;
  height: 100%;
  overflow-x: hidden; /* Prevent horizontal scrolling */
  margin: 0;
  padding: 0;
}

/* Videos Container */
.videos {
  display: flex; /* Align children in a row */
  gap: 1rem; /* Add spacing between videos */
  overflow-x: auto; /* Enable horizontal scrolling */
  padding: 1rem; /* Add padding for better spacing */
  scrollbar-width: thin; /* Thin scrollbar for Firefox */
  scroll-snap-type: x mandatory; /* Enable snapping for smooth scrolling */
}

.videos::-webkit-scrollbar {
  height: 8px; /* Customize scrollbar height for WebKit browsers */
}

.videos::-webkit-scrollbar-thumb {
  background: #888; /* Scrollbar color */
}

.videos::-webkit-scrollbar-thumb:hover {
  background: #555; /* Hover color for scrollbar */
}

/* Individual Video Block */
.video {
  flex: 0 0 auto; /* Prevent shrinking */
  width: 45%; /* Default width for videos (mobile-friendly) */
  scroll-snap-align: start; /* Align items for snapping */
}

.video video {
  display: block; /* Prevent extra inline spacing */
  width: 100%; /* Ensure videos fit within the container */
  margin: 0;
}

.projects {
  padding-top: 10px;
  padding-bottom: 40px;
}

.project_title {
  font-family: 'Manrope', sans-serif;
  color: white;
  text-align: center;
  font-size: 0.9rem; /* Smaller font for mobile */
  margin-top: 0.5rem;
}

/* Modal Styles */
.video_player,
.modal_background {
  position: fixed;
  width: auto;
  height: 90%;
  max-height: 100vh; /* Ensure modal fits within the viewport */
  z-index: 4;
  opacity: 1;
  display: flex;
  justify-content: center;
  overflow: hidden;
  margin: 0 auto;
}

/* Responsive Adjustments */
@media (min-width: 768px) {
  .video {
    width: 300px; /* Larger width for tablet screens */
  }

  .videos {
    padding: 1rem 2rem; /* Add more padding for tablets */
  }

  .project_title {
    font-size: 1rem; /* Adjust title size for tablet */
  }
}

@media (min-width: 1024px) {
  .video {
    width: 400px; /* Larger width for desktop screens */
  }

  .videos {
    gap: 1.5rem; /* More space between videos */
  }

  .project_title {
    font-size: 1.2rem; /* Slightly larger titles for desktop */
  }
}

@media (max-width: 767px) {
  .videos {
    padding: 0 1rem; /* Avoid extra horizontal spacing */
  }

  .video {
    width: calc(50% - 1rem); /* Adjust for mobile (2 videos per row) */
  }

  .video video {
    width: 100%; /* Ensure video fits the container */
  }

  .project_title {
    font-size: 0.8rem; /* Smaller font for mobile screens */
  }
}

/* Utility Classes */
.project_type {
  padding: 20px;
  overflow-y: none;
  color: white;
}

.project_type h2 {
  text-align: left;
  font-size: 2rem;
  font-family: 'Manrope', sans-serif;
  font-weight: bold;
}

.project_type .video_grid {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
}

.project_type .video_grid .video_block video {
  max-height: 200px; /* Limit video height */
  width: 100%;
  filter: grayscale(0.4);
  transition: filter 1s ease;
}

.project_type .video_grid .video_block:hover video {
  filter: grayscale(0);
}

.project_type .video_grid .project_title {
  font-weight: bold;
  cursor: pointer;
  font-size: 1rem;
  color: white;
}

.project_type .video_grid .video_block {
  text-align: center;
}

/* Footer (Optional Styling) */
footer {
  margin: 0;
  padding: 0;
  height: auto;
  display: flex;
  justify-content: center;
  align-items: center;
  background: black;
  color: white;
}
</style>
