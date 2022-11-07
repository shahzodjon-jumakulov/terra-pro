<template>
  <hero-banner></hero-banner>
  <div class="container">
    <div class="cards">
      <div
        class="card-item"
        v-for="card in cards"
        :key="card.key"
        :style="'background-image: url(' + card.src + ')'"
      >
        <h2>
          {{ card.title }}
        </h2>
      </div>
    </div>
  </div>
</template>

<script>
import HeroBanner from "../components/homePage/HeroBanner.vue";

export default {
  components: {
    HeroBanner,
  },
  data() {
    return {
      cards: [
        {
          title: "Толстовки и Джогеры",
          src: "../assets/card-1.png",
        },
        {
          title: "Толстовки и Джогеры",
          src: "../assets/card-1.png",
        },
        {
          title: "Толстовки и Джогеры",
          src: "../assets/card-1.png",
        },
        {
          title: "Толстовки и Джогеры",
          src: "../assets/card-1.png",
        },
        {
          title: "Толстовки и Джогеры",
          src: "../assets/card-1.png",
        },
        {
          title: "Толстовки и Джогеры",
          src: "../assets/card-1.png",
        },
      ],
    };
  },
};
</script>

<style scoped>
.card-item {
}
</style>

