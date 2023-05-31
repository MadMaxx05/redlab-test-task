<script setup></script>

<template>
  <section class="hero">
    <div class="hero__wrapper">
      <div class="hero__image animate"></div>
      <div class="hero__text">
        <h1 class="animate">Доставка готової їжі в Києві</h1>
        <p style="transition-delay: 0.15s" class="animate">
          Ми пропонуємо доставку їжі прямо до ваших дверей. Насолоджуйтесь смачними стравами без
          необхідності готувати самостійно.
        </p>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  padding-top: 130px;
  height: 100%;
}

.hero__wrapper {
  display: flex;
  flex-direction: column;
}

.hero__image {
  background-image: url('../assets/images/hero-image.jpg');
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  height: 400px;
  width: 100%;
  order: 2;
}

.hero__text {
  margin-bottom: 70px;
  padding: 0 20px;
  order: 1;
}

.hero__text h1 {
  margin: 0 auto 30px;
  font-size: 45px;
  font-weight: 400;
  line-height: 110%;
  color: #404040;
  max-width: 500px;
}

.hero__text p {
  margin: 0 auto;
  font-size: 18px;
  line-height: 25px;
  color: #404040;
  max-width: 500px;
}

@media (min-width: 1024px) {
  .hero {
    padding: 0;
  }
  .hero__wrapper {
    display: flex;
    flex-direction: row;
    align-items: center;
  }

  .hero__wrapper > div {
    flex: 0 0 50%;
    max-width: 50%;
  }

  .hero .hero__image {
    order: 1;
    height: 100vh;
    min-height: 500px;
  }

  .hero .hero__text {
    margin: 0;
    order: 2;
  }

  .hero .hero__text h1 {
    font-size: 60px;
    max-width: 397px;
  }

  .hero .hero__text p {
    max-width: 397px;
  }
}

@media (min-width: 1280px) {
  .hero__text h1 {
    font-size: 76px;
  }
}
</style>
