<template>
  <hero-banner></hero-banner>
  <div class="container">
    <div class="cards">
      <div class="card-item" v-for="card in sections" :key="card.key">
        <figure>
          <div class="overlay"></div>
          <img :src="require('../assets/' + card.src)" alt="" />
          <div class="text">
            <h2>{{ card.title }}</h2>
            <a href="#">Смотреть еще</a>
          </div>
        </figure>
      </div>
    </div>
    <div class="show-more" @click="moreSections = true" v-if="!moreSections">
      Показать больше
    </div>
    <div class="show-more" @click="moreSections = false" v-else>
      Показать меньше
    </div>
  </div>
  <home-products
    v-for="title in productsTitles"
    :key="title.key"
    :productsTitle="title.name"
  ></home-products>
  <user-comments></user-comments>
</template>

<script>
import HeroBanner from "../components/homePage/HeroBanner.vue";
import HomeProducts from "../components/homePage/HomeProducts.vue";
import UserComments from "../components/homePage/UserComments.vue";

export default {
  components: {
    HeroBanner,
    HomeProducts,
    UserComments,
  },
  data() {
    return {
      cards: [
        {
          title: "Толстовки и Джогеры",
          src: "card-1.png",
        },
        {
          title: "Поло и Брюки",
          src: "card-2.png",
        },
        {
          title: "Футболки",
          src: "card-3.png",
        },
        {
          title: "Футболки",
          src: "card-3.png",
        },
        {
          title: "Толстовки и Джогеры",
          src: "card-1.png",
        },
        {
          title: "Поло и Брюки",
          src: "card-2.png",
        },
        {
          title: "Поло и Брюки",
          src: "card-2.png",
        },
        {
          title: "Толстовки и Джогеры",
          src: "card-1.png",
        },
        {
          title: "Футболки",
          src: "card-3.png",
        },
        {
          title: "Толстовки и Джогеры",
          src: "card-1.png",
        },
        {
          title: "Поло и Брюки",
          src: "card-2.png",
        },
        {
          title: "Футболки",
          src: "card-3.png",
        },
      ],
      moreSections: false,
      productsTitles: [
        {
          name: "Товары со скидкой",
        },
        {
          name: "Новая коллекция",
        },
        {
          name: "Хиты продаж",
        },
      ],
    };
  },
  computed: {
    sections() {
      if (!this.moreSections) {
        return this.cards.slice(0, 6);
      } else {
        return this.cards.slice(0, this.cards.length);
      }
    },
  },
};
</script>

<style scoped>
.card-item {
  position: relative;
  overflow: hidden;
  display: flex;
  flex: 33%;
  padding: 1px;
  cursor: pointer;
}

.card-item figure {
  position: relative;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
}

.card-item figure > img {
  width: 100%;
}

.text {
  position: absolute;
  left: 56px;
  bottom: 56px;
}

.text h2 {
  font-weight: 600;
  font-size: 40px;
  line-height: 47px;
  color: #ffffff;
  width: 220px;
  margin-bottom: 22px;
}

.text a {
  font-weight: 600;
  font-size: 16px;
  line-height: 19px;
  color: #ffffff;
}

.cards {
  display: flex;
  flex-flow: row;
  flex-wrap: wrap;
  justify-content: center;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0);
  transition: background 0.5s ease;
}

.card-item:hover .overlay {
  display: block;
  background: rgba(0, 0, 0, 0.3);
}

.show-more {
  font-weight: 600;
  font-size: 20px;
  line-height: 24px;
  color: #242424;
  background: #f2f2f2;
  text-align: center;
  padding: 24px 0;
  cursor: pointer;
  transition: all 0.3s ease-in-out;
  margin-top: -1px;
}

.show-more:hover {
  background: #242424;
  color: #ffffff;
}
</style>

