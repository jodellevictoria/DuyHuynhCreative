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
        <div>
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source
              src="/src/assets/sports/180829-MLS-FEA-OSO RE-SIGN v3 (2020_09_29 00_42_32 UTC).mp4"
              type="video/mp4"
            />
          </video>
          <span>MLS Osorio Contract Extension</span>
        </div>
        <div>
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source src="/src/assets/sports/220516-TORvsDAL Narrative Spot.mp4" type="video/mp4" />
          </video>
          <span>Toronto Arrows</span>
        </div>
        <div>
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source src="/src/assets/sports/NBA-TWT-190520-RAPTORS TAILGATE.mp4" type="video/mp4" />
          </video>
          <span>Toronto Raptors Tailgate</span>
        </div>
        <div>
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source src="/src/assets/sports/240606 - CCYAA_CC_Hilites.mp4" type="video/mp4" />
          </video>
          <span>CCYAA Celebrity Classic 2023</span>
        </div>
      </div>
    </div>
    <div id="products" class="project_type">
      <h2>Products</h2>
      <div class="video_grid">
        <div>
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source src="/src/assets/products/1080_30s_Sapporo Spot v2.mp4" type="video/mp4" />
          </video>
          <span>Sapporo Spot</span>
        </div>
        <div>
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source src="/src/assets/products/1080_30s_Whiskey Spot.mp4" type="video/mp4" />
          </video>
          <span>Whiskey Spot</span>
        </div>
        <div>
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source
              src="/src/assets/products/200507-KNU-WEB-Free Shipping 30 SEC Spot B TITLE.mp4"
              type="video/mp4"
            />
          </video>
          <span>Knurling Dental</span>
        </div>
        <div>
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source
              src="/src/assets/products/230720-16x9 Summer Travel Drinks v10 EN.mp4"
              type="video/mp4"
            />
          </video>
          <span>Air Canada - Summer Travel Drinks</span>
        </div>
      </div>
    </div>
    <div id="branding" class="project_type">
      <h2>Brand Content</h2>
      <div class="video_grid">
        <div>
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source
              src="/src/assets/branding/230725-EN169-Free Wifi Concept v5 ONB.mp4"
              type="video/mp4"
            />
          </video>
          <span>Air Canada Free Wifi</span>
        </div>
        <div>
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source
              src="/src/assets/branding/Air Canada Celebrating Disney and Pixar’s new film, Turning Red.mp4"
              type="video/mp4"
            />
          </video>
          <span>Air Canada X Disney & Pixar's film, Turning Red</span>
        </div>
        <div>
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source src="/src/assets/branding/TEAS-BHM 1st Piece v6 EN.mp4" type="video/mp4" />
          </video>
          <span>Air Canada: To the next generation in aviation</span>
        </div>
        <div>
          <video muted loop onmouseover="this.play()" onmouseout="this.pause()" class="grayscale">
            <source
              src="/src/assets/branding/230328-Rosemary Flight Sim S+D v3.mp4"
              type="video/mp4"
            />
          </video>
          <span>Air Canada Black History Month</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
/**
 *
 * TODO: Start Mobile
 *
 * Fade in from 1 2 3
 */
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
