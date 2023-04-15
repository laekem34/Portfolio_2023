<template>
  <router-view />
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "App",
  
});
</script>

<style>
body {
  width: 100%;
  height: 100%;
  background: linear-gradient(90deg, #97a0c9 0%, #e9d0c8 100%);
}
@font-face {
  font-family: "Roboto Flex";
  src: url("../public/fonts/RobotoFlex.woff2") format("woff2-variations");
  font-weight: 400;
  font-style: normal;
  font-variation-settings: "wght" 400, "opsz" 100%;
}

a {
  text-decoration: none;
  color: black;
}
</style>
