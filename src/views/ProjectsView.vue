<template>
  <div>
    <div v-if="modal_active == true">
      <div
        style="
          background-color: black;
          height: 100vh;
          width: 100vw;
          opacity: 0.7;
          z-index: 3;
          position: fixed;
          backdrop-filter: blur(20px);
        "
        @click="stop_watching"
      ></div>
      <video
        id="videoplayer"
        ref="videoplayer"
        controls
        autoplay
        style="
          position: fixed;
          width: 90%;
          height: 90%;
          opacity: 1;
          z-index: 4;
          display: flex;
          justify-content: center;
          margin-left: 5%;
          margin-right: 5%;
          margin-top: 5%;
        "
      >
        <source :src="video_in_modal.link" type="video/mp4" />
      </video>
      <!-- <video muted autoplay class="vid_player">
        <source :src="video_in_modal.link" type="video/mp4" />
      </video> -->
    </div>
    <div class="projects">
      <div class="full-width-container">
        <div class="inner-div" @click="this.$refs.sports.scrollIntoView({ behavior: 'smooth' })">
          <video
            id="sports_bg"
            muted
            loop
            onmouseover="this.play()"
            onmouseout="this.pause()"
            class="grayscale"
          >
            <source src="/src/assets/SportsBGAnim.mov" type="video/mp4" />
          </video>
          <div class="text">SPORTS</div>
        </div>
        <div class="inner-div" @click="this.$refs.products.scrollIntoView({ behavior: 'smooth' })">
          <video
            id="sports_bg"
            muted
            loop
            onmouseover="this.play()"
            onmouseout="this.pause()"
            class="grayscale"
          >
            <source src="/src/assets/ProductBGAnim.mov" type="video/mp4" />
          </video>
          <div class="text">PRODUCTS</div>
        </div>
        <div class="inner-div" @click="this.$refs.branding.scrollIntoView({ behavior: 'smooth' })">
          <video
            id="sports_bg"
            muted
            loop
            onmouseover="this.play()"
            onmouseout="this.pause()"
            class="grayscale"
          >
            <source src="/src/assets/BrandingBGAnim.mov" type="video/mp4" />
          </video>
          <div class="text">BRAND CONTENT</div>
        </div>
      </div>
      <div id="sports" ref="sports" class="project_type">
        <h2>Sports</h2>
        <div class="video_grid">
          <div
            v-for="(video, index) in sports_videos"
            v-bind:key="index"
            class="video_block"
            @click="watch_video(video)"
          >
            <video muted loop onmouseover="this.play()" onmouseout="this.pause()">
              <source :src="video.link" type="video/mp4" />
            </video>
            <!-- <img style="max-width: 650px" :src="`src/assets${video.src}`" /> -->
            <span class="project_title">{{ video.name }}</span>
          </div>
        </div>
      </div>
      <div id="products" ref="products" class="project_type">
        <h2>Products</h2>
        <div class="video_grid">
          <div
            v-for="(video, index) in product_videos"
            v-bind:key="index"
            class="video_block"
            @click="watch_video(video)"
          >
            <video muted loop onmouseover="this.play()" onmouseout="this.pause()">
              <source :src="video.link" type="video/mp4" />
            </video>
            <!-- <img style="max-width: 650px" :src="`src/assets${video.src}`" /> -->
            <span class="project_title">{{ video.name }}</span>
          </div>
        </div>
      </div>
      <div id="branding" ref="branding" class="project_type">
        <h2>Brand Content</h2>
        <div class="video_grid">
          <div
            v-for="(video, index) in branding_videos"
            v-bind:key="index"
            class="video_block"
            @click="watch_video(video)"
          >
            <video muted loop onmouseover="this.play()" onmouseout="this.pause()">
              <source :src="video.link" type="video/mp4" />
            </video>
            <!-- <img style="max-width: 650px" :src="`src/assets${video.src}`" /> -->
            <span class="project_title">{{ video.name }}</span>
          </div>
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
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@200..800&display=swap');

.full-width-container {
  animation: fadeInAnimation ease 3s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  display: flex;
  max-width: 100vw;
  height: 100vh; /* Full viewport height */
  /*justify-content: space-around;*/
  align-items: center;
}

.inner-div {
  position: relative;
  width: 33.33%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;

  .grayscale {
    filter: grayscale(0.25);
    -webkit-filter: grayscale(0.25);
    filter: grayscale(25%);
    transition: all 1s ease;
  }

  .grayscale:hover {
    transition: all 1s ease;
    /*animation: recolor ease 5s;*/
    filter: grayscale(0);
    -webkit-filter: grayscale(0);
    filter: grayscale(0%);
  }
}

.inner-div:hover {
  cursor: pointer;
}

.background-video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0;
  transition: opacity 0.5s ease-in-out;
}

.inner-div:hover .background-video {
  opacity: 1;
}

.text {
  position: absolute;
  z-index: 1;
  font-size: 60px;
  color: white;
  font-family: Deuterium;
  font-weight: 500;
  writing-mode: vertical-lr;
}
@keyframes fadeInAnimation {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
.project_type {
  animation: fadeInAnimation ease 1s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  overflow-y: none;
  overflow-x: scroll;

  -ms-overflow-style: none; /* Internet Explorer 10+ */
  scrollbar-width: none;

  padding-top: 50px;
  padding-bottom: 50px;
  color: white;

  h2 {
    font-size: 70px;
    font-weight: 500;
    font-family: Deuterium;
  }

  .video_grid {
    display: flex;
    /* padding-left: auto;
    padding-right: auto; */
    gap: 20px;

    /* .project_title:hover {
      font-weight: bold;
      cursor: pointer;
    } */

    .video_block {
      /* img {
        filter: grayscale(0.4);
        -webkit-filter: grayscale(0.4);
        filter: grayscale(40%);
      } */

      video {
        max-height: 300px;
        filter: grayscale(0.4);
        -webkit-filter: grayscale(0.4);
        filter: grayscale(40%);
        transition: all 1s ease;
      }

      .project_title {
        font-family: 'Manrope';
      }
    }

    .video_block:hover {
      cursor: pointer;
      video {
        transition: all 1s ease;

        filter: grayscale(0);
        -webkit-filter: grayscale(0);
        filter: grayscale(0%);
      }
      .project_title {
        font-weight: bold;
      }
    }
  }
}

.project_type::-webkit-scrollbar {
  display: none; /* Safari and Chrome */
}

.modal_background {
  position: fixed; /* Stay in place front is invalid - may break your css so removed */
  z-index: 4;
  height: 100vh;
  width: 100vw;
  background-color: black;
}

.vid_player {
  width: 90%;
  height: 90%;
  z-index: 5;
  opacity: 1;
}

.visible {
  visibility: visible;
}
.invisible {
  visibility: hidden;
}
</style>
