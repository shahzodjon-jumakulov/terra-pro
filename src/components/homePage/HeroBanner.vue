<template>
  <div class="banner">
    <div class="text">
      <h2>urban runaway</h2>
      <button>узнать больше</button>
    </div>
  </div>
  <div class="container">
    <div class="features">
      <div class="item" v-for="feature in features" :key="feature.key">
        <img :src="require('../../assets/' + feature.src)" :alt=feature.alt />
        <p> {{ feature.name }} </p>
      </div>
    </div>
    <div class="sections">
      <div class="section-item" v-for="section in sections" :key="section.key">
        <img :src="require('../../assets/' + section.src)" alt="section" />
        <p>{{ section.name }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      features: [
        {
          name: "Покупка товаров в рассрочку",
          src: "feature-1.svg",
          alt: "loan",
        },
        {
          name: "Легкий возврат товаров",
          src: "feature-2.svg",
          alt: "mail",
        },
        {
          name: "Бесплатная доставка от 300 000 сум",
          src: "feature-3.svg",
          alt: "delivery",
        },
        {
          name: "Доставка по всему Узбекистану",
          src: "feature-4.svg",
          alt: "delivery",
        },
        {
          name: "Доступные цены",
          src: "feature-5.svg",
          alt: "costs",
        },
      ],
      sections: [
        {
          name: "Чиносы",
          src: "section-1.png",
        },
        {
          name: "Толстовки",
          src: "section-2.png",
        },
        {
          name: "Ветровки",
          src: "section-3.png",
        },
        {
          name: "Кеды",
          src: "section-4.png",
        },
        {
          name: "Джинсы",
          src: "section-5.png",
        },
        {
          name: "Рюкзаки",
          src: "section-6.png",
        },
      ],
    };
  },
};
</script>

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