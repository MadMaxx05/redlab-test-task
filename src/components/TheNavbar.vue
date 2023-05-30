<script setup>
import MobileNavigation from './MobileNavigation.vue'

import { ref, onMounted, onUnmounted } from 'vue'

const scrollPosition = ref(0)
const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
  document.body.classList.toggle('menu-open', isMenuOpen.value)
}

onMounted(() => {
  window.addEventListener('scroll', () => {
    scrollPosition.value = window.scrollY
  })
})

onUnmounted(() => {
  window.removeEventListener('scroll', () => {
    scrollPosition.value = window.scrollY
  })
})
</script>

<template>
  <header :class="{ scrolled: scrollPosition > 0 }">
    <div class="header__wrapper">
      <div class="header__logo">
        <div>
          <a href="/">
            <img src="../assets/images/logo.svg" alt="Logo" />
          </a>
        </div>
        <div class="header__switch">
          <a class="active" href="#">Доставка</a>
          <a href="#">Самовивіз</a>
        </div>
      </div>
      <nav class="header-menu">
        <ul>
          <li>
            <a href="#">Заклади</a>
          </li>
          <li>
            <a href="#">Доставка і оплата</a>
          </li>
          <li>
            <a href="#">Акції</a>
          </li>
          <li>
            <a href="#">Про нас</a>
          </li>
        </ul>
      </nav>
      <div class="header-right">
        <div class="header__contact">
          <a href="tel:+380674519957">+380 67 451 99 57</a>
          <span class="header__contact__divider"></span>
          <span>24/7</span>
        </div>
        <button @click="toggleMenu" :class="{ 'menu-open': isMenuOpen }" class="menu-btn">
          <span></span>
          <span></span>
        </button>
      </div>
    </div>
    <MobileNavigation :isMenuOpen="isMenuOpen" />
  </header>
</template>

<style scoped>
header {
  position: fixed;
  top: 0;
  z-index: 50;
  width: 100%;
  transition: all 300ms;
}

header.scrolled {
  background-color: white;
  box-shadow: 0px 2px 14px rgba(0, 0, 0, 0.07);
}

.header__wrapper {
  padding: 16px 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.header__logo {
  display: flex;
  align-items: center;
  gap: 30px;
}

.header__switch {
  display: none;
  gap: 3px;
  padding: 3px;
  background-color: white;
  border: 1px solid #e2e8f0;
  border-radius: 50px;
}

.header__switch a {
  display: inline-block;
  padding: 8px 12px;
  text-decoration: none;
  font-size: 14px;
  font-weight: 600;
  line-height: 15.4px;
  color: #636c81;
  transition: color 300ms;
}

.header__switch a.active {
  border-radius: 50px;
  background-color: #5a30f0;
  color: white;
}

.header__switch a:not(.active):hover {
  color: #5a30f0;
}

.header-menu {
  display: none;
  margin-left: -130px;
}

.header-menu ul {
  display: flex;
  align-items: center;
  gap: 32px;
  list-style-type: none;
}

.header-menu ul li a {
  font-size: 16px;
  font-weight: 500;
  line-height: 19px;
  letter-spacing: 0.2px;
  color: #404040;
  transition: color 300ms;
}

.header-menu ul li a:hover {
  color: #5a30f0;
}

.header-right {
  display: flex;
  align-items: center;
  gap: 30px;
}

.header__contact {
  display: none;
  align-items: center;
  gap: 15px;
  font-size: 16px;
  font-weight: 600;
  line-height: 19px;
  letter-spacing: 0.2px;
  color: #404040;
}

.header__contact a {
  transition: color 300ms;
}

.header__contact a:hover {
  color: #5a30f0;
}

.header__contact__divider {
  height: 14px;
  width: 2px;
  background-color: #404040;
}

.menu-btn {
  position: relative;
  display: block;
  width: 30px;
  height: 30px;
  background-color: transparent;
  cursor: pointer;
  z-index: 50;
}

.menu-btn span {
  position: absolute;
  width: 25px;
  height: 2px;
  background-color: #404040;
  transition: all 300ms ease;
}

.menu-btn span:first-child {
  top: 10px;
  left: 50%;
  transform: translateX(-50%);
}

.menu-btn span:last-child {
  bottom: 10px;
  left: 50%;
  transform: translateX(-50%);
}

.menu-btn.menu-open span {
  background-color: white;
}

.menu-btn.menu-open span:first-child {
  top: 14px;
  transform: translateX(-50%) rotate(45deg);
}

.menu-btn.menu-open span:last-child {
  bottom: 14px;
  transform: translateX(-50%) rotate(-45deg);
}

@media (min-width: 768px) {
  .header__wrapper {
    padding: 16px 50px;
  }

  .header__switch,
  .header__contact {
    display: flex;
  }
}

@media (min-width: 1280px) {
  .header-menu {
    display: block;
  }

  .menu-btn {
    display: none;
  }
}
</style>
