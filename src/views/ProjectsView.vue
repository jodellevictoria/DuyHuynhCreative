<template>
  <div class="projects">
    <div id="projects_intro">
      <section id="sports_link" @click="scrollTo">
        <a href="#sports">
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
          <span class="heading">SPORTS</span>
        </a>
      </section>
      <section id="products_link">
        <a href="#products">
          <video
            id="products_bg"
            muted
            loop
            onmouseover="this.play()"
            onmouseout="this.pause()"
            class="grayscale"
          >
            <source src="/src/assets/ProductBGAnim.mov" type="video/mp4" />
          </video>
          <span class="heading">PRODUCTS</span>
        </a>
      </section>
      <section id="brandings_link">
        <a href="#branding">
          <video
            id="brandings_bg"
            muted
            loop
            onmouseover="this.play()"
            onmouseout="this.pause()"
            class="grayscale"
          >
            <source src="/src/assets/Branding_BG.mov" type="video/mp4" />
          </video>
          <span class="heading">BRAND CONTENT</span>
        </a>
      </section>
    </div>
    <div id="sports" class="project_type">
      <h2>Sports</h2>
      <div class="video_grid">
        <div v-for="(video, index) in sports_videos" v-bind:key="index">
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source :src="video.link" type="video/mp4" />
          </video>
          <span>{{ video.name }}</span>
        </div>
      </div>
    </div>
    <div id="products" class="project_type">
      <h2>Products</h2>
      <div class="video_grid">
        <div v-for="(video, index) in product_videos" v-bind:key="index">
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source :src="video.link" type="video/mp4" />
          </video>
          <span>{{ video.name }}</span>
        </div>
      </div>
    </div>
    <div id="branding" class="project_type">
      <h2>Brand Content</h2>
      <div class="video_grid">
        <div v-for="(video, index) in branding_videos" v-bind:key="index">
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source :src="video.link" type="video/mp4" />
          </video>
          <span>{{ video.name }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
/**
 *
 * TODO: Start Mobile
 *
 * Fade in from 1 2 3
 */

const sports_videos = [
  {
    name: 'MLS Osorio Contract Extension',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/sports%2F180829-MLS-FEA-OSO%20RE-SIGN%20v3%20(2020_09_29%2000_42_32%20UTC).mp4?alt=media&token=a948555a-854c-4512-ad8b-5aa7987c8870',
    roles: ['', '']
  },
  {
    name: 'Toronto Arrows',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/sports%2F220516-TORvsDAL%20Narrative%20Spot.mp4?alt=media&token=cb729d4e-bbc0-4c78-af9b-674d86f83485',
    roles: ['', '']
  },
  {
    name: 'Toronto Raptors Tailgate',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/sports%2FNBA-TWT-190520-RAPTORS%20TAILGATE.mp4?alt=media&token=d94a340c-6dcd-4ac8-9bed-800310c45a50',
    roles: ['', '']
  },
  {
    name: 'CCYAA Celebrity Classic 2023',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/sports%2F240606%20-%20CCYAA_CC_Hilites.mp4?alt=media&token=adbc3a20-6467-4573-a7c8-1db83d08b44a',
    roles: ['', '']
  }
]

const product_videos = [
  {
    name: 'Sapporo Spot',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/product%2F1080_30s_Sapporo%20Spot%20v2.mp4?alt=media&token=f5f14096-1cce-4585-9715-82daeb4dfd38',
    roles: ['', '']
  },
  {
    name: 'Whiskey Spot',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/product%2F1080_30s_Whiskey%20Spot.mp4?alt=media&token=674529ca-e225-441b-9ab7-e4a2f1d20b93',
    roles: ['', '']
  },
  {
    name: 'Knurling Dental',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/product%2F200507-KNU-WEB-Free%20Shipping%2030%20SEC%20Spot%20B%20TITLE.mp4?alt=media&token=cbd34609-9750-43e5-95b2-649ddf7a23b7',
    roles: ['', '']
  },
  {
    name: 'Air Canada - Summer Travel Drinks',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/product%2F230720-16x9%20Summer%20Travel%20Drinks%20v10%20EN.mp4?alt=media&token=62def7be-2f95-4f8f-9a53-3dee9e3eda9c',
    roles: ['', '']
  }
]

const branding_videos = [
  {
    name: 'Air Canada Free Wifi',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/branding%2F230725-EN169-Free%20Wifi%20Concept%20v5%20ONB.mp4?alt=media&token=410bac4a-2839-43b8-9c58-2b360959ad75',
    roles: ['', '']
  },
  {
    name: "Air Canada X Disney & Pixar's film, Turning Red",
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/branding%2FAir%20Canada%20Celebrating%20Disney%20and%20Pixar%E2%80%99s%20new%20film%2C%20Turning%20Red.mp4?alt=media&token=6954555f-864a-4fb2-888c-473a277fa152',
    roles: ['', '']
  },
  {
    name: 'Air Canada: To the next generation in aviation',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/branding%2F230328-Rosemary%20Flight%20Sim%20S%2BD%20v3.mp4?alt=media&token=92854419-b44a-4dcb-9ad6-4a500c50f0e5',
    roles: ['', '']
  },
  {
    name: "Air Canada: Zoey's Story",
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/branding%2F231107-Zoeys%20Story%20v15.2%20EN.mp4?alt=media&token=5d0a6167-7cc0-4534-8fdb-3c6081a79c63',
    roles: ['', '']
  },
  {
    name: 'Air Canada Black History Month',
    link: 'https://firebasestorage.googleapis.com/v0/b/duyhuynhportfolio.appspot.com/o/branding%2FTEAS-BHM%201st%20Piece%20v6%20EN.mp4?alt=media&token=d6e89776-d66b-4a45-88c8-5e35f2b45dd5',
    roles: ['', '']
  }
]
</script>

<style>
@keyframes fadeInAnimation {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
.projects {
  animation: fadeInAnimation ease 3s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
  top: 64px;
  background-color: black;
  max-width: 100% !important;
  display: grid;
  grid-template-rows: auto auto auto auto;
}

#projects_intro {
  max-width: 100% !important;
  min-height: 800px;
  display: grid;
  grid-template-columns: 32.5vw 32.5vw 32.5vw;
}

section {
  width: 33%;
  height: 100%;
  cursor: pointer;

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

  video {
    height: 100%;
    position: absolute;
    z-index: 0;
  }

  .heading {
    background: transparent;
    position: absolute;
    width: 400px;
    height: 20px;
    margin-top: 20%;
    margin-bottom: 20%;
    z-index: 2;
    font-weight: bold;
    color: white;

    transform: rotate(-90deg);
    font-size: 40px;
  }
}

.section:hover {
  transform: scale(1.2);
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
    font-weight: bold;
  }

  .video_grid {
    display: flex;
    /* padding-left: auto;
    padding-right: auto; */
    gap: 20px;

    video {
      max-height: 300px;
      cursor: pointer;
    }
  }
}

.project_type::-webkit-scrollbar {
  display: none; /* Safari and Chrome */
}
</style>
