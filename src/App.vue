<template>
  <app-header></app-header>
  <app-home></app-home>
  <app-footer></app-footer>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import AppFooter from "./components/AppFooter.vue";
import AppHome from "./pages/AppHome.vue";

export default {
  components: {
    AppHeader,
    AppFooter,
    AppHome,
  },
};
</script>

<style>
/* fonts */
@font-face {
  font-family: "TT Hoves";
  src: local("TT Hoves Regular"), local("TT-Hoves-Regular"),
    url("./fonts/TTHoves-Regular.woff2") format("woff2"),
    url("./fonts/TTHoves-Regular.woff") format("woff"),
    url("./fonts/TTHoves-Regular.ttf") format("truetype");
  font-weight: 400;
  font-style: normal;
}

@font-face {
  font-family: "TT Hoves";
  src: local("TT Hoves Medium"), local("TT-Hoves-Medium"),
    url("./fonts/TTHoves-Medium.woff2") format("woff2"),
    url("./fonts/TTHoves-Medium.woff") format("woff"),
    url("./fonts/TTHoves-Medium.ttf") format("truetype");
  font-weight: 500;
  font-style: normal;
}

@font-face {
  font-family: "TT Hoves";
  src: local("TT Hoves DemiBold"), local("TT-Hoves-DemiBold"),
    url("./fonts/TTHoves-DemiBold.woff2") format("woff2"),
    url("./fonts/TTHoves-DemiBold.woff") format("woff"),
    url("./fonts/TTHoves-DemiBold.ttf") format("truetype");
  font-weight: 600;
  font-style: normal;
}

@font-face {
  font-family: "TT Hoves";
  src: local("TT Hoves Bold"), local("TT-Hoves-Bold"),
    url("./fonts/TTHoves-Bold.woff2") format("woff2"),
    url("./fonts/TTHoves-Bold.woff") format("woff"),
    url("./fonts/TTHoves-Bold.ttf") format("truetype");
  font-weight: 700;
  font-style: normal;
}

@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@600;700&display=swap');

*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  font-family: "TT Hoves";
}

.container {
  max-width: 1280px;
  margin: 0 auto;
}
</style>