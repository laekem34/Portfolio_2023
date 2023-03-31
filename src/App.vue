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
</style>
