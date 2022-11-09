<template>
  <div class="container">
    <div class="section">
      <div class="title">
        <h2 class="section-title"> {{ productsTitle }} </h2>
        <a href="#">
          Смотреть все
          <svg
            width="14"
            height="11"
            viewBox="0 0 14 11"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M1.66683 5.5H12.3335"
              stroke="#242424"
              stroke-width="1.5"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
            <path
              d="M7.00016 10.1663L12.3335 5.49967L7.00016 0.833008"
              stroke="#242424"
              stroke-width="1.5"
              stroke-linecap="round"
              stroke-linejoin="round"
            />
          </svg>
        </a>
      </div>
      <div class="cards">
        <div
          v-for="product in products"
          :key="product.key"
          class="card-item"
          @mouseover="product.isHovered = true"
          @mouseleave="product.isHovered = false"
        >
          <div class="top-stick">Только на сайте</div>
          <div class="fav">
            <svg
              width="30"
              height="28"
              viewBox="0 0 30 28"
              :fill="product.isFav ? '#ff0000' : '#828282'"
              xmlns="http://www.w3.org/2000/svg"
              @click="
                product.isFav ? (product.isFav = false) : (product.isFav = true)
              "
            >
              <path
                d="M27.6867 3.02452C26.9537 2.27711 26.0833 1.68422 25.1254 1.27971C24.1675 0.875195 23.1407 0.666992 22.1038 0.666992C21.0669 0.666992 20.0402 0.875195 19.0822 1.27971C18.1243 1.68422 17.254 2.27711 16.5209 3.02452L14.9996 4.57492L13.4783 3.02452C11.9976 1.51552 9.98941 0.667774 7.89541 0.667774C5.80142 0.667774 3.79319 1.51552 2.31251 3.02452C0.831836 4.53352 1.56015e-08 6.58016 0 8.7142C-1.56015e-08 10.8482 0.831836 12.8949 2.31251 14.4039L3.83382 15.9543L14.9996 27.3337L26.1654 15.9543L27.6867 14.4039C28.4201 13.6568 29.0019 12.7698 29.3988 11.7936C29.7957 10.8173 30 9.77095 30 8.7142C30 7.65746 29.7957 6.61107 29.3988 5.63482C29.0019 4.65856 28.4201 3.77157 27.6867 3.02452V3.02452Z"
              />
            </svg>
          </div>
          <div class="preview" v-if="product.isHovered">
            <svg
              width="22"
              height="16"
              viewBox="0 0 22 16"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M20.257 6.962C20.731 7.582 20.731 8.419 20.257 9.038C18.764 10.987 15.182 15 11 15C6.81801 15 3.23601 10.987 1.74301 9.038C1.51239 8.74113 1.38721 8.37592 1.38721 8C1.38721 7.62408 1.51239 7.25887 1.74301 6.962C3.23601 5.013 6.81801 1 11 1C15.182 1 18.764 5.013 20.257 6.962V6.962Z"
                stroke="#828282"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
              <path
                d="M11 11C12.6569 11 14 9.65685 14 8C14 6.34315 12.6569 5 11 5C9.34315 5 8 6.34315 8 8C8 9.65685 9.34315 11 11 11Z"
                stroke="#828282"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
            </svg>
            Быстрый просмотр
          </div>
          <img
            :src="
              product.isHovered
                ? require('../../assets/' + product.imgHovered)
                : require('../../assets/' + product.img)
            "
            alt="product"
          />
          <div class="text">
            <div class="menu" v-if="product.isHovered">
              <button class="addCart">Добавить в корзину</button>
              <div class="size">
                <span
                  class="size-item"
                  :class="product.size === 'xs' ? 'active' : null"
                  @click="product.size = 'xs'"
                  >XS</span
                >
                <span
                  class="size-item"
                  :class="product.size === 's' ? 'active' : null"
                  @click="product.size = 's'"
                  >S</span
                >
                <span
                  class="size-item"
                  :class="product.size === 'm' ? 'active' : null"
                  @click="product.size = 'm'"
                  >M</span
                >
                <span
                  class="size-item"
                  :class="product.size === 'l' ? 'active' : null"
                  @click="product.size = 'l'"
                  >L</span
                >
              </div>
            </div>
            <p class="product-title">Футболка короткий рукав</p>
            <div class="color">
              <button
                class="color-item black"
                :class="product.color === 'black' ? 'active' : null"
                @click="product.color = 'black'"
              ></button>
              <button
                class="color-item orange"
                :class="product.color === 'orange' ? 'active' : null"
                @click="product.color = 'orange'"
              ></button>
            </div>
            <div class="cost">
              <div class="previous-cost">{{ product.prevPrice }} сум</div>
              <div class="current-cost">{{ product.currentPrice }} сум</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        {
          imgSrc: "product-white-1.png",
          prevPrice: "169 990",
          currentPrice: "89 990",
          color: "black",
          isHovered: false,
          size: "",
          isFav: false,
          img: "product-white-1.png",
          imgHovered: "product-white-2.png",
        },
        {
          imgSrc: "../../assets/product-white-1.png",
          prevPrice: "169 990",
          currentPrice: "89 990",
          color: "black",
          isHovered: false,
          size: "",
          isFav: false,
          img: "product-black-1.png",
          imgHovered: "product-black-2.png",
        },
        {
          imgSrc: "../../assets/product-white-1.png",
          prevPrice: "169 990",
          currentPrice: "89 990",
          color: "black",
          isHovered: false,
          size: "",
          isFav: false,
          img: "product-white-1.png",
          imgHovered: "product-white-2.png",
        },
        {
          imgSrc: "../../assets/product-white-1.png",
          prevPrice: "169 990",
          currentPrice: "89 990",
          color: "black",
          isHovered: false,
          size: "",
          isFav: false,
          img: "product-black-1.png",
          imgHovered: "product-black-2.png",
        },
      ],
    };
  },
  props: [
      'productsTitle',
  ]
};
</script>

<style scoped>
.container {
  margin: 120px auto;
}

.title {
  display: flex;
  justify-content: space-between;
  margin-bottom: 32px;
}

.section-title {
  font-weight: 500;
  font-size: 40px;
  line-height: 47px;
  color: #242424;
  margin: auto 0;
}

.section a {
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
  color: #242424;
  margin: auto 0;
  text-decoration: none;
}

.section a svg {
  margin-left: 5px;
}

.cards {
  display: flex;
  flex-flow: row;
  flex-wrap: wrap;
  justify-content: center;
}

.card-item {
  position: relative;
  overflow: hidden;
  flex: 24%;
  cursor: pointer;
  transition: all 0.3s ease-in-out;
}

.card-item + .card-item {
  margin-left: 9px;
}

.card-item img {
  width: 100%;
  outline: none;
  transition: all 0.3s ease-in-out;
}

.text {
  padding: 12px 16px;
  position: relative;
}

.product-title {
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
  color: #242424;
}

.color {
  display: flex;
  margin: 8px 0;
}

.color-item {
  width: 16px;
  height: 16px;
  margin: auto 0;
  margin-right: 20px;
  border: none;
  cursor: pointer;
  position: relative;
}

.color-item.black {
  background-color: #000000;
  border-radius: 50%;
}

.color-item.orange {
  background-color: #de6353;
  border-radius: 50%;
}

.color-item.active:before {
  content: "";
  position: absolute;
  width: 18px;
  height: 18px;
  border-radius: 50%;
  border: 2px solid #828282;
  text-align: 0;
  top: -3px;
  left: -3px;
}

.cost {
  display: flex;
}

.previous-cost {
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
  text-decoration-line: line-through;
  color: #828282;
  margin-right: 32px;
}

.current-cost {
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
  color: #242424;
}

.menu {
  position: absolute;
  width: 100%;
  left: 0;
  top: -78px;
  padding: 8px 16px;
  background: rgba(255, 255, 255, 0.8);
  backdrop-filter: blur(2px);
  transition: all 0.3s ease-in-out;
}

.addCart {
  margin-bottom: 8px;
  padding: 8px 16px;
  background-color: #ffffff;
  border: none;
  color: rgba(36, 36, 36, 0.8);
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
}

.addCart:hover {
  color: #242424;
}

.size {
  font-weight: 500;
  font-size: 16px;
  line-height: 19px;
  color: rgba(36, 36, 36, 0.8);
}

.size-item {
  padding: 4px 12px;
  font-weight: 400;
  font-size: 16px;
  line-height: 19px;
  color: #242424;
}

.size-item:hover,
.size-item.active {
  background: #e0e0e0;
}

.size-item + .size-item {
  margin-left: 32px;
}

.fav {
  position: absolute;
  right: 8px;
  top: 8px;
}

.top-stick {
  position: absolute;
  top: 0;
  left: 0;
  background: rgba(242, 242, 242, 0.8);
  border-radius: 0px 0px 8px 0px;
  padding: 10px 16px;
  text-align: center;
  width: 65px;
}

.preview {
  position: absolute;
  top: 37%;
  left: 12%;
  background: rgba(255, 255, 255, 0.9);
  border-radius: 500px;
  padding: 16px 32px;
}
</style>