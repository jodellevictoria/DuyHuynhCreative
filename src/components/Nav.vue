<template>
  <div class="navigator">
    <span>
      <b><RouterLink to="/">Duy Huynh</RouterLink></b>
    </span>
    <div class="v-tabs-bar">
      <button class="dropbtn">
        <RouterLink to="/">Home</RouterLink>
      </button>
      <div class="dropdown">
        <button class="dropbtn"><RouterLink to="/projects">Projects</RouterLink></button>
        <div class="dropdown-content">
          <RouterLink to="/projects" v-scroll-to="'#sports'">Sports</RouterLink>
          <RouterLink to="/projects" v-scroll-to="'#products'">Products</RouterLink>
          <RouterLink to="/projects" v-scroll-to="'#brandings'">Brand Content</RouterLink>
        </div>
      </div>
      <button class="dropbtn">
        <RouterLink to="/about">About</RouterLink>
      </button>
      <button class="dropbtn">
        <RouterLink to="/contact">Contact</RouterLink>
      </button>
    </div>
  </div>
</template>

<script>
/**
 * TODO: Mobile Nav & Stick Nav while Scroll
 */
import { RouterLink } from 'vue-router'

export default {
  data: () => ({})
}
</script>
<style>
.navigator {
  position: fixed;

  top: 0;
  width: 100%;
  background: black;
  padding: 20px 40px 20px 40px;
  color: white;
  z-index: 1;
}

/* Links inside the navbar */
.navigator a {
  float: left;
  color: white;
  text-align: center;
  text-decoration: none;
}

.navigator a:hover {
  font-weight: bold;
}

.dropbtn {
  border: none;
  outline: none;
  color: white;
  background-color: inherit;
  font-family: inherit; /* Important for vertical align on mobile phones */
  margin: 0; /* Important for vertical align on mobile phones */
}

.v-tabs-bar {
  float: right !important;
  display: flex;
  gap: 40px;
}

.tabs {
  display: flex;
  gap: 40px;
}

.v-tab {
  text-transform: none !important;
}

/* The dropdown container */
.dropdown {
  margin-top: 5px;
  float: left;
  overflow: hidden;
}

/* Dropdown content (hidden by default) */
.dropdown-content {
  padding-top: 10px;
  display: none;
  position: absolute;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  z-index: 1;
  animation: growDown 500ms ease-in-out forwards;
  transform-origin: top center;
}

@keyframes growDown {
  0% {
    transform: scaleY(0);
  }
  80% {
    transform: scaleY(1.1);
  }
  100% {
    transform: scaleY(1);
  }
}

/* Links inside the dropdown */
.dropdown-content a {
  float: none;
  background-color: black;
  color: white;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  text-align: left;
}

/* Show the dropdown menu on hover */
.dropdown:hover .dropdown-content {
  display: flex;
  flex-direction: column;
}
</style>
