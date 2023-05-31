<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  const button = document.querySelector('.magnetic-btn')

  button.addEventListener('mousemove', (e) => {
    const position = button.getBoundingClientRect()

    const x = e.pageX - position.left - position.width / 2
    const y = e.pageY - (position.top + window.scrollY) - position.height / 2

    button.style.transform = `translate(${x}px, ${y}px)`
  })

  button.addEventListener('mouseout', () => {
    button.style.transform = 'translate(0px, 0px)'
  })
})
</script>

<template>
  <div class="magnetic-btn__wrapper">
    <div class="magnetic-btn__inner">
      <button class="magnetic-btn">
        <span class="magnetic-btn__background"></span>
        <span class="magnetic-btn__text">Замовити доставку</span>
      </button>
    </div>
  </div>
</template>

<style>
.magnetic-btn__wrapper {
  position: fixed;
  inset: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
}

.magnetic-btn__inner {
  position: absolute;
  bottom: 10px;
  right: 10px;
  transition: bottom 500ms ease;
}

.magnetic-btn {
  outline: 0;
  background-color: transparent;
  width: 140px;
  height: 140px;
  border-radius: 100%;
  font-size: 14px;
  line-height: 130%;
  font-weight: 600;
  color: white;
  text-transform: uppercase;
  letter-spacing: 2px;
  cursor: pointer;
  pointer-events: auto;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: all 200ms ease;
}

.magnetic-btn__background {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #5a30f0;
  border-radius: 100%;
  transition: transform 500ms ease;
}

.magnetic-btn:hover .magnetic-btn__background {
  transform: scale(1.3);
}

.magnetic-btn__text {
  position: relative;
  animation: rotate 30s linear infinite;
}

@media (min-width: 1024px) {
  .magnetic-btn {
    width: 195px;
    height: 195px;
    font-size: 18px;
  }

  .magnetic-btn__inner {
    bottom: 15px;
    right: 50%;
    transform: translateX(50%);
  }

  .scrolled ~ .magnetic-btn__wrapper .magnetic-btn__inner {
    bottom: -45px;
  }
}

@keyframes rotate {
  0% {
    transform: rotate(0);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
