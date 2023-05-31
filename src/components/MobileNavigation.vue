<script setup>
defineProps({
  isMenuOpen: Boolean
})
</script>

<template>
  <div class="mobile-navigation" :class="{ 'menu-open': isMenuOpen }">
    <div>
      <nav>
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
      <div class="mobile-navigation__contact">
        <a href="tel:+380674519957">+380 67 451 99 57</a>
        <span class="mobile-navigation__divider"></span>
        <span>24/7</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.mobile-navigation {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 5;
  transition: all 300ms ease;
}

.mobile-navigation.menu-open {
  pointer-events: auto;
}

.mobile-navigation > div {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 30vh 20px 70px;
  position: fixed;
  background-color: #5a30f0;
  height: 100vh;
  width: 100%;
  transform: translateX(100%);
  top: 0;
  right: 0;
  transition: all 300ms ease;
  z-index: 10;
}

.mobile-navigation.menu-open > div {
  transform: translateX(0);
}

.mobile-navigation::after {
  content: '';
  display: block;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(255, 255, 255, 0.5);
  backdrop-filter: blur(2px);
  opacity: 0;
  pointer-events: none;
  transition: all 300ms ease;
}

.mobile-navigation.menu-open::after {
  opacity: 1;
  pointer-events: auto;
}

.mobile-navigation ul {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 30px;
  list-style-type: none;
}

.mobile-navigation ul li {
  font-size: 32px;
  line-height: 110%;
  letter-spacing: 0.2px;
  color: white;
  transition: all 300ms ease;
}

.mobile-navigation ul li:hover {
  transform: scale(1.1);
  font-weight: 500;
}

.mobile-navigation__contact {
  margin-top: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 20px;
  font-size: 20px;
  line-height: 110%;
  letter-spacing: 0.2px;
  color: white;
}

.mobile-navigation__divider {
  height: 14px;
  width: 2px;
  background-color: white;
}

.mobile-navigation__contact a {
  transition: all 300ms ease;
}

.mobile-navigation__contact a:hover {
  transform: scale(1.1);
  font-weight: 500;
}

@media (min-width: 768px) {
  .mobile-navigation > div {
    width: 500px;
    transform: translateX(500px);
  }

  .header__switch,
  .mobile-navigation__contact {
    display: none;
  }
}
</style>
