<template>
  <div class="projects">
    <div id="projects_intro" style="height: 2000px">
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
    <div id="sports" style="height: 2000px">Sports</div>
    <div id="products" style="height: 2000px">Products</div>
    <div id="branding" style="height: 2000px">Brand Content</div>
  </div>
</template>

<script>
/**
 *
 * TODO: Start Mobile
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
  width: 100%;
  height: auto;
  background-color: black;
}

#projects_intro {
  display: flex;
}

section {
  width: 33%;
  height: 100%;
  cursor: pointer;
  /* 
  @keyframes recolor {
    0% {
      filter: grayscale(1);
      -webkit-filter: grayscale(1);
      filter: grayscale(100%);
    }
    50% {
      filter: grayscale(0.25);
      -webkit-filter: grayscale(0.25);
      filter: grayscale(25%);
    }
    100% {
      filter: grayscale(0);
      -webkit-filter: grayscale(0);
      filter: grayscale(0%);
    }
  } */

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
</style>
