<template>
  <header :class="{ scrolled: isScrolled }">
    <div class="container">
      <div class="logo">
        <RouterLink to="/">
          <img src="@/assets/images/Logo.png" alt="Logo" />
        </RouterLink>
      </div>

      <div class="menu-toggle" @click="toggleMenu">☰</div>

      <nav :class="{ active: menuOpen }">
        <ul>
          <li><RouterLink to="/">Home</RouterLink></li>
          <li><RouterLink to="/About">About</RouterLink></li>
          <li><RouterLink to="/Project">Projects</RouterLink></li>
          <li><RouterLink to="/Service">Services</RouterLink></li>
          <li><RouterLink to="#">News</RouterLink></li>
          <li><RouterLink to="#">Contact</RouterLink></li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const menuOpen = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleMenu = () => {
  menuOpen.value = !menuOpen.value
}

onMounted(() => {
  handleScroll()
  window.addEventListener('scroll', handleScroll)
})
onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<style scoped>
/* Reset & container */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.container {
  max-width: 1200px;
  width: 100%;
  padding: 0 24px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

/* Header default (transparent) */
header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  padding: 20px 0;
  background-color: transparent;
  transition: background-color 0.3s ease, box-shadow 0.3s ease;
  z-index: 1000;
}

/* Header when scrolled */
header.scrolled {
  background-color: #333;
  box-shadow: 0 2px 10px rgba(255, 254, 254, 0.2);
}

.logo img {
  height: 40px;
  transition: filter 0.3s ease;
}
/* đổi màu chữ logo */
/* header.scrolled .logo img {
   filter: invert(1);  
} */

/* Navigation styles */
nav ul {
  list-style: none;
  display: flex;
  gap: 30px;
}

nav ul li a {
  color: white;
  text-decoration: none;
  font-size: 13px;
  text-transform: uppercase;
  letter-spacing: 1px;
  transition: color 0.3s ease;
}

header.scrolled nav ul li a {
  color: #ffffff;
}

/* Toggle button (mobile) */
.menu-toggle {
  display: none;
  font-size: 28px;
  color: white;
  cursor: pointer;
}

/* Responsive */
@media (max-width: 768px) {
  .menu-toggle {
    display: block;
  }

  nav {
    position: absolute;
    top: 70px;
    left: 0;
    width: 100%;
    background-color: #333;
    display: none;
    padding: 20px 0;
  }

  nav.active {
    display: block;
  }

  nav ul {
    flex-direction: column;
    align-items: center;
    gap: 20px;
  }
}
</style>
