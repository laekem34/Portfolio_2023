<template>
  <div class="q-pa-xs-sm q-pa-md-lg">
    <q-layout
      id="card-bg"
      class="card g-white text-black shadow-10 rounded-border-30"
    >
      <NavCard @variable-changed="handleVariableChange" />
      <HeaderCard />
      <p>Variable reçue : {{ receivedVariable }}</p>
    </q-layout>
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";
import HeaderCard from "src/components/HeaderCard.vue";
import NavCard from "src/components/NavCard.vue";

export default defineComponent({
  name: "FirstCard",
  components: {
    HeaderCard,
    NavCard,
  },
  data() {
    return {
      receivedVariable: "",
    };
  },
  methods: {
    handleVariableChange(variable) {
      this.receivedVariable = variable;
    },
  },
  setup() {
    const selectedLanguage = ref("FR");
    function onLanguageChanged(lang) {
      selectedLanguage.value = lang; // Mettez à jour la valeur de selectedLanguage
    }
    return {
      selectedLanguage,
      onLanguageChanged,
    };
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

#card-bg {
  /* background-image: linear-gradient(135deg,rgba(6, 44, 102) 0%,
                                    rgba(0, 255, 178) 200%),
                    linear-gradient(to bottom, rgba(255, 255, 255, 0.5), rgba(255, 255, 255, 0.5)); */
  background-color: white;
  background-size: cover;
  background-repeat: no-repeat;
}
</style>
