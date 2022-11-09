<template>
  <div class="container">
    <div class="header-top">
      <div class="header-logo">
        <a href="/" class="logo">
          <img src="../assets/header-logo.png" alt="logo" />
        </a>
        <p>Доставка по Узбекистану</p>
      </div>
      <div class="header-top-nav">
        <div class="header-contact">
          <h6>+998 71 2509391</h6>
          <p>Пн. – Сб. : с 09:00 до 19:00</p>
        </div>
        <div class="header-icons">
          <div class="header-icon-item search">
            <img src="../assets/header-search.svg" alt="search" />
            <p>Поиск</p>
          </div>
          <div class="header-icon-item cart">
            <img src="../assets/header-cart.svg" alt="cart" />
            <p>Корзина</p>
          </div>
          <div class="header-icon-item fav">
            <img src="../assets/header-fav.svg" alt="favorite" />
            <p>Избранное</p>
          </div>
          <div class="header-icon-item profile">
            <img src="../assets/header-profile.svg" alt="profile" />
            <p>(97) 777-66-99</p>
          </div>
        </div>
        <div class="header-lang" @click="langIsOpen = !langIsOpen">
          <img src="../assets/header-lang-ru.png" alt="language" class="ru" />
          <p>
            RU
            <img src="../assets/arrow-down.svg" alt="" class="arrow" />
          </p>
          <div class="lang-menu" v-if="langIsOpen">
            <div class="lang-ru">Русский</div>
            <div class="lang-uz">O’zbek</div>
          </div>
        </div>
      </div>
    </div>
    <div class="header-nav full-width">
      <div class="gender">
        <button
          class="gender-item"
          @click="gender = 'male'"
          :class="gender === 'male' ? 'active' : null"
        >
          Мужчины
        </button>
        <button
          class="gender-item"
          @click="gender = 'female'"
          :class="gender === 'female' ? 'active' : null"
        >
          Женщины
        </button>
      </div>
      <div class="navbar">
        <div class="nav-item">
          <img src="../assets/header-menu.svg" alt="" />
          Каталог одежды
        </div>
        <div class="nav-item">Товары со скидкой</div>
        <div class="nav-item">Новая коллекция</div>
        <div class="nav-item">О компании</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      gender: "male",
      langIsOpen: false,
    };
  },
};
</script>

<style scoped>
/* top */

.header-top {
  display: flex;
  justify-content: space-between;
  padding: 12px 0;
}

.header-logo {
  margin: auto 0;
}

.header-logo p {
  margin-left: 5px;
}

.header-logo p {
  font-weight: 600;
  font-size: 14px;
  line-height: 14px;
  letter-spacing: 0.05em;
  color: #bdbdbd;
}

.header-top-nav {
  display: flex;
  justify-content: space-between;
  width: 790px;
}

.header-contact {
  text-align: right;
  margin: auto 0;
}

.header-contact h6 {
  font-weight: 600;
  font-size: 16px;
  line-height: 19px;
  color: #242424;
  position: relative;
}

.header-contact h6:before {
  content: "";
  position: absolute;
  background-image: url("../assets/header-phone.svg");
  width: 13px;
  height: 13px;
  left: 18px;
  top: 2px;
}

.header-contact p {
  font-weight: 600;
  font-size: 13px;
  line-height: 14px;
  color: #bdbdbd;
}

.header-icons {
  display: flex;
  justify-content: space-between;
  width: 390px;
}

.header-icon-item {
  margin: auto 0;
  cursor: pointer;
  color: #828282;
  transition: all .3s ease-in-out;
}

.header-icon-item:hover {
  color: #242424;
}

.header-icon-item img {
  width: 24px;
  height: 24px;
  display: block;
  margin: 0 auto 4px;
}

.header-icon-item p {
  font-weight: 600;
  font-size: 14px;
  line-height: 14px;
}

.header-lang {
  position: relative;
  cursor: pointer;
}

.header-lang .ru {
  width: 28px;
  height: 28px;
  display: block;
  margin: 0 auto 4px;
}

.header-lang p {
  font-weight: 600;
  font-size: 14px;
  line-height: 16px;
  color: #828282;
  position: relative;
}

.lang-menu {
  background: rgba(36, 36, 36, 0.95);
  border-radius: 4px;
  padding: 24px;
  font-weight: 600;
  font-size: 16px;
  line-height: 19px;
  color: #ffffff;
  position: absolute;
  z-index: 3;
  text-align: center;
  top: 55px;
  left: -40px;
}

.lang-ru {
  margin-bottom: 24px;
}

/* navbar */

.header-nav {
  font-family: "Montserrat", sans-serif;
  display: flex;
  justify-content: space-between;
  background-color: #383b47;
}

.full-width {
  box-shadow: 0 0 0 100vmax #383b47;
  clip-path: inset(0 -100vmax);
}

.gender-item {
  font-weight: 600;
  font-size: 16px;
  line-height: 14px;
  color: #ffffff;
  width: 165px;
  height: 50px;
  background-color: transparent;
  border: none;
  outline: none;
  cursor: pointer;
}

.gender-item.active {
  background-color: #0d7377;
}

.navbar {
  display: flex;
  justify-content: space-between;
  font-weight: 700;
  font-size: 14px;
  line-height: 14px;
  color: #ffffff;
}

.nav-item {
  margin: auto 0;
  cursor: pointer;
}

.nav-item img {
  margin-right: 12px;
}

.nav-item + .nav-item {
  margin-left: 72px;
}
</style>