<script setup></script>

<template>
  <section class="features">
    <div class="features__container">
      <div class="features__item">
        <h3>Висока якість продукції</h3>
        <div>
          <img src="../assets/images/check.svg" alt="Check" />
        </div>
        <div class="features__tip">
          Наша доставка гарантує вам високу якість продуктів. Кожна страва, яку ми готуємо, пройшла
          строгий контроль якості, щоб забезпечити вам найкращий смаковий досвід.
        </div>
      </div>
      <div class="features__item">
        <h3>Різноманітність страв</h3>
        <div>
          <img src="../assets/images/bowl.svg" alt="Bowl" />
        </div>
        <div class="features__tip">
          Наша доставка гарантує вам високу якість продуктів. Кожна страва, яку ми готуємо, пройшла
          строгий контроль якості, щоб забезпечити вам найкращий смаковий досвід.
        </div>
      </div>
      <div class="features__item">
        <h3>Швидка доставка</h3>
        <div>
          <img src="../assets/images/rocket.svg" alt="Rocket" />
        </div>
        <div class="features__tip">
          Наша доставка гарантує вам високу якість продуктів. Кожна страва, яку ми готуємо, пройшла
          строгий контроль якості, щоб забезпечити вам найкращий смаковий досвід.
        </div>
      </div>
      <div class="features__item">
        <h3>Працюємо цілодобово</h3>
        <div>
          <img src="../assets/images/clock.svg" alt="Clock" />
        </div>
        <div class="features__tip">
          Наша доставка гарантує вам високу якість продуктів. Кожна страва, яку ми готуємо, пройшла
          строгий контроль якості, щоб забезпечити вам найкращий смаковий досвід.
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.features {
  padding: 73px 0;
}

.features__container {
  margin: 0 auto;
  padding: 0 20px;
  max-width: 1400px;
  display: grid;
  gap: 20px;
}

.features__item {
  position: relative;
  padding: 20px;
  background-color: #f3f6fb;
  border-radius: 8px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  overflow: hidden;
}

.features__tip {
  position: absolute;
  inset: 0;
  padding: 30px;
  font-size: 16px;
  line-height: 22.4px;
  color: white;
  background-color: #5a30f0;
  z-index: 2;
  opacity: 0;
  user-select: none;
  transition: opacity 300ms ease;
}

.features__tip:hover {
  opacity: 1;
  user-select: auto;
}

.features__item h3 {
  margin: 0 auto;
  max-width: 270px;
  font-size: 24px;
  text-align: center;
  font-weight: 500;
  color: #404040;
  line-height: 31.2px;
}

.features__item img {
  width: 120px;
  height: 120px;
}

@media (min-width: 576px) {
  .features__container {
    grid-template-columns: repeat(2, minmax(0, 2fr));
  }
}

@media (min-width: 1024px) {
  .features__container {
    grid-template-columns: repeat(4, minmax(0, 1fr));
    gap: 40px;
  }

  .features__item img {
    width: 190px;
    height: 190px;
  }
}
</style>
