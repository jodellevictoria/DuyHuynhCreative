<template>
  <div class="navigator">
    <span>
      <b><RouterLink to="/">Duy Huynh Creative</RouterLink></b>
    </span>
    <div class="hamburger-menu" @click="toggleMenu">&#9776;</div>
    <div class="v-tabs-bar" :class="{ show: menuOpen }">
      <button class="dropbtn">
        <RouterLink to="/">Home</RouterLink>
      </button>
      <button class="dropbtn">
        <RouterLink to="/about">About</RouterLink>
      </button>
      <div class="dropdown desktop">
        <button class="dropbtn">
          <RouterLink to="/projects">Projects</RouterLink>
        </button>
        <div class="dropdown-content">
          <RouterLink to="/projects" v-scroll-to="'#sports'">Sports</RouterLink>
          <RouterLink to="/projects" v-scroll-to="'#products'">Products</RouterLink>
          <RouterLink to="/projects" v-scroll-to="'#brandings'">Brand Content</RouterLink>
        </div>
      </div>
      <button class="dropbtn mobile">
        <RouterLink to="/projects">Projects</RouterLink>
      </button>
      <button class="dropbtn">
        <RouterLink to="/contact">Contact</RouterLink>
      </button>
    </div>
  </div>
</template>

<script>
import { RouterLink } from 'vue-router'

export default {
  data() {
    return {
      menuOpen: false
    }
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@200..800&display=swap');

.navigator {
  font-family: 'Manrope';
  position: fixed;
  top: 0;
  width: 100%;
  background: black;
  padding: 20px 40px 20px 40px;
  color: white;
  z-index: 2;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navigator a {
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
  font-family: inherit;
  margin: 0;
}

.v-tabs-bar {
  display: flex;
  gap: 20px;
  align-items: center;
}

.dropdown {
  position: relative;
}

.dropdown-content {
  display: none;
  position: absolute;
  text-align: left;
  background-color: black;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  z-index: 1;
  flex-direction: column;
  opacity: 0;
  transform: translateY(-20px); /* Start with a slight upward offset */
  transition:
    opacity 0.3s ease,
    transform 0.3s ease;
  animation: none;
}
.dropdown-content a {
  color: white;
  font-size: 14px;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  text-align: left; /* Explicitly align text to the left */
}

.dropdown:hover .dropdown-content {
  display: flex;
  animation: slideDown 0.3s ease forwards;
}

@keyframes slideDown {
  0% {
    opacity: 0;
    transform: translateY(-20px); /* Start from a slight upward position */
  }
  100% {
    opacity: 1;
    transform: translateY(0); /* End at the original position */
  }
}

.hamburger-menu {
  display: none;
  font-size: 30px;
  cursor: pointer;
}

.v-tabs-bar.show {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 20px;
}

.mobile {
  display: none;
}

.desktop {
  display: block;
}

@media (max-width: 768px) {
  .hamburger-menu {
    display: block;
  }

  .v-tabs-bar {
    display: none;
    position: absolute;
    top: 70px;
    left: 0;
    right: 0;
    background-color: black;
    padding: 20px;
    z-index: 1;
    flex-direction: column;
    gap: 20px;
  }

  .v-tabs-bar.show {
    display: flex;
  }

  .dropdown-content {
    display: none;
  }

  .dropdown-content.show {
    display: flex;
  }

  .mobile {
    display: block;
  }

  .desktop {
    display: none;
  }
}
</style>
