<template>
  <div class="banner">
    <div class="text">
      <h2>urban runaway</h2>
      <button>узнать больше</button>
    </div>
  </div>
  <div class="container">
    <div class="features">
      <div class="item">
        <img src="../../assets/feature-1.svg" alt="loan" />
        <p>Покупка товаров в рассрочку</p>
      </div>
      <div class="item">
        <img src="../../assets/feature-2.svg" alt="mail" />
        <p>Легкий возврат товаров</p>
      </div>
      <div class="item">
        <img src="../../assets/feature-3.svg" alt="delivery" />
        <p>Бесплатная доставка от 300 000 сум</p>
      </div>
      <div class="item">
        <img src="../../assets/feature-4.svg" alt="delivery" />
        <p>Доставка по всему Узбекистану</p>
      </div>
      <div class="item">
        <img src="../../assets/feature-5.svg" alt="costs" />
        <p>Доступные цены</p>
      </div>
    </div>
    <div class="sections">
      <div class="section-item">
        <img src="../../assets/section-1.png" alt="section" />
        <p>Чиносы</p>
      </div>
      <div class="section-item">
        <img src="../../assets/section-2.png" alt="section" />
        <p>Толстовки</p>
      </div>
      <div class="section-item">
        <img src="../../assets/section-3.png" alt="section" />
        <p>Ветровки</p>
      </div>
      <div class="section-item">
        <img src="../../assets/section-4.png" alt="section" />
        <p>Кеды</p>
      </div>
      <div class="section-item">
        <img src="../../assets/section-5.png" alt="section" />
        <p>Джинсы</p>
      </div>
      <div class="section-item">
        <img src="../../assets/section-6.png" alt="section" />
        <p>Рюкзаки</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.banner {
  background-image: url("../../assets/hero-banner.png");
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
  height: 100vh;
}

.text {
  text-align: center;
  color: white;
  text-transform: uppercase;
  width: max-content;
  margin: auto;
  padding-top: 15%;
}

.text h2 {
  font-weight: 700;
  font-size: 100px;
}

.text button {
  font-weight: 600;
  font-size: 16px;
  line-height: 19px;
  border: none;
  padding: 16px 32px;
  background-color: #242424;
  text-transform: uppercase;
  gap: 10px;
  border-radius: 2px;
  color: #ffffff;
  margin-top: 60px;
  transition: 0.3s ease-in-out;
  cursor: pointer;
}

.text button:hover {
  color: #242424;
  background-color: #ffffff;
}

/* FEATURES */

.features {
  display: flex;
  justify-content: space-around;
  margin: 40px 0;
}

.features .item {
  box-shadow: 0px 4px 40px rgba(38, 41, 43, 0.07);
  border-radius: 12px;
  background: #ffffff;
  padding: 32px 16px;
  text-align: center;
  width: 296px;
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
  color: #242424;
}

.item + .item {
  margin-left: 64px;
}

/* SECTION   */

.sections {
  display: flex;
  justify-content: space-between;
  margin-bottom: 40px;
  text-align: center;
}

.section-item {
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
  color: #242424;
  cursor: pointer;
  transition: 0.5s ease-in-out;
  
}

.section-item:hover {
  transform: scale(1.05);
}
</style>