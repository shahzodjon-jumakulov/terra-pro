<template>
  <div class="container">
    <carousel :items-to-show="3" :wrapAround="true" :modelValue="1">
      <template #addons>
        <div class="comment-top">
          <h2 class="title">Отзывы клиентов</h2>
          <navigation />
        </div>
      </template>
      <slide v-for="slide in slides" :key="slide.key">
        <div class="comment-block">
          <div class="profile">
            <img :src="require('../../assets/' + slide.avatar)" alt="avatar" />
            <div class="name-date">
              <div class="username">{{ slide.userName }}</div>
              <div class="date">
                {{ slide.postedDay }}, {{ slide.postedTime }}
              </div>
            </div>
          </div>
          <div class="product-name">{{ slide.productName }}</div>
          <div class="rating-pic">
            Соответсвие фото:
            <span>
              <img src="../../assets/star.svg" alt="star" />
              <img src="../../assets/star.svg" alt="star" />
              <img src="../../assets/star.svg" alt="star" />
              <img src="../../assets/star.svg" alt="star" />
              <img src="../../assets/star.svg" alt="star" />
            </span>
          </div>
          <div class="rating-qual">
            Качество товара:
            <span>
              <img src="../../assets/star.svg" alt="star" />
              <img src="../../assets/star.svg" alt="star" />
              <img src="../../assets/star.svg" alt="star" />
              <img src="../../assets/star.svg" alt="star" />
              <img src="../../assets/star.svg" alt="star" />
            </span>
          </div>
          <div class="description">{{ slide.comment }}</div>
        </div>
      </slide>
    </carousel>
    <div class="about-us">
      <h2 class="title">О компании TERRA PRO</h2>
      <p class="desc">
        Terra Pro является одним из крупнейших брендов мужской одежды в сфере
        FAST-fashion, основанным в 2012 году.
      </p>
      <p class="desc">
        Особенностью компании является дизайнерский подход и скорость, с которой
        новые линейки проходят путь от разработки до старта продаж.
      </p>
      <p class="desc">
        Мы создаем простую индивидуальность, сочетая качество с доступной ценой,
        давая нашим потребителям лучшее. Целевой аудиторией бренда Terra Pro
        являются активные молодые люди в возрасте от 18 до 35 лет.
      </p>
    </div>
  </div>
</template>

<script>
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Navigation } from "vue3-carousel";

export default {
  components: {
    Carousel,
    Slide,
    Navigation,
  },
  data() {
    return {
      slides: [
        {
          userName: "Анвар Джаббаров",
          postedDay: "Сегодня",
          postedTime: "13:46",
          productName: "Рубашка длинный рукав",
          ratingPic: 5,
          ratingQuality: 5,
          comment:
            "Все в семье довольны качеством одежды, ну а я также еще и радуюсь доступности предоставляемой вами продукции . . .",
          avatar: "user-avatar.png",
        },
        {
          userName: "Анвар Джаббаров",
          postedDay: "Сегодня",
          postedTime: "14:46",
          productName: "Рубашка длинный рукав",
          ratingPic: 5,
          ratingQuality: 5,
          comment:
            "Все в семье довольны качеством одежды, ну а я также еще и радуюсь доступности предоставляемой вами продукции . . .",
          avatar: "user-avatar.png",
        },
        {
          userName: "Анвар Джаббаров",
          postedDay: "Сегодня",
          postedTime: "15:46",
          productName: "Рубашка длинный рукав",
          ratingPic: 5,
          ratingQuality: 5,
          comment:
            "Все в семье довольны качеством одежды, ну а я также еще и радуюсь доступности предоставляемой вами продукции . . .",
          avatar: "user-avatar.png",
        },
        {
          userName: "Анвар Джаббаров",
          postedDay: "Сегодня",
          postedTime: "16:46",
          productName: "Рубашка длинный рукав",
          ratingPic: 5,
          ratingQuality: 5,
          comment:
            "Все в семье довольны качеством одежды, ну а я также еще и радуюсь доступности предоставляемой вами продукции . . .",
          avatar: "user-avatar.png",
        },
      ],
    };
  },
};
</script>

<style scoped>
.comment-block {
  text-align: left;
  width: 320px;
}

.comment-top {
  display: flex;
  justify-content: space-between;
  position: absolute;
  top: 0;
  width: 100%;
}

.comment-top .title {
  font-weight: 600;
  font-size: 24px;
  line-height: 28px;
  color: #242424;
}

.comment-top span {
  margin-left: 15px;
  cursor: pointer;
}

.comment-top span svg:hover {
  fill: #242424;
}

.carousel {
  padding-top: 110px;
}

.profile {
  display: flex;
}

.name-date {
  margin-left: 16px;
}

.username {
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
  color: #242424;
}

.date {
  font-weight: 500;
  font-size: 14px;
  line-height: 16px;
  color: #828282;
  margin-top: 8px;
}

.product-name {
  font-weight: 600;
  font-size: 18px;
  line-height: 21px;
  color: #242424;
  margin: 32px 0 24px;
}

.rating-pic,
.rating-qual {
  font-weight: 500;
  font-size: 14px;
  line-height: 16px;
  color: #242424;
  margin-bottom: 6px;
  display: flex;
  justify-content: space-between;
}

.rating-pic span,
.rating-qual span {
  vertical-align: middle;
  margin-right: 80px;
}

.description {
  font-weight: 500;
  font-size: 16px;
  line-height: 140%;
  color: #828282;
  margin-top: 24px;
}

.about-us {
    margin: 120px 0;
}

.about-us .title {
  font-weight: 600;
  font-size: 24px;
  line-height: 28px;
  color: #242424;
  margin-bottom: 40px;
}

.about-us .desc {
  font-weight: 400;
  font-size: 20px;
  line-height: 140%;
  color: #242424;
}

.desc + .desc {
    margin-top: 30px;
}
</style>

<style>
.carousel__prev {
  right: 30px;
  left: unset;
}
</style>