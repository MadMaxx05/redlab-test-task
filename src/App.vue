<script setup>
import { onMounted } from 'vue'

import TheNavbar from './components/TheNavbar.vue'
import HeroSection from './components/HeroSection.vue'
import FeaturesSection from './components/FeaturesSection.vue'

onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        entry.target.classList.add('animated')
      }
    })
  })

  const items = document.querySelectorAll('.animate')
  items.forEach((item) => {
    observer.observe(item)
  })
})
</script>

<template>
  <TheNavbar />
  <HeroSection />
  <FeaturesSection />
</template>

<style>
.animate {
  transform: translateY(100px);
  opacity: 0;
}

.animated {
  transform: translateY(0);
  opacity: 1;
  transition: all 1s ease;
}
</style>
