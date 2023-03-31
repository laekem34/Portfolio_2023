<template>
  <div class="q-pa-xs-sm q-pa-md-lg">
    <q-layout class="card bg-white text-black shadow-10 rounded-border-30">
      <NavCard />
      <HeaderCard />
    </q-layout>
  </div>
</template>

<script>
import { defineComponent } from "vue";
import HeaderCard from "src/components/HeaderCard.vue";
import NavCard from "src/components/NavCard.vue";

export default defineComponent({
  name: "FirstCard",
  components: {
    HeaderCard,
    NavCard,
  },
});
</script>

<style scoped>
.rounded-border-30 {
  border-radius: 30px;
}
.card {
  background-size: 80%;
  min-height: fit-content !important;
}
</style>
