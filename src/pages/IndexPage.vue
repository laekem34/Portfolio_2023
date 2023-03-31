<template>
  <Card />
  <ThePortfolio />
</template>

<script>
import { defineComponent } from "vue";
import Card from "src/components/Card.vue";
import ThePortfolio from "src/components/Portfolio.vue";

export default defineComponent({
  name: "IndexPage",
  components: {
    Card,
    ThePortfolio,
  },
});
</script>
