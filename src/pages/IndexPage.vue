<template>
  <Card @variable-changed="handleVariableChangeB" />

  <ThePortfolio :receivedVariable="receivedVariable" />
  <TheContact :receivedVariable="receivedVariable" />
</template>

<script>
import { defineComponent } from "vue";
import Card from "src/components/Card.vue";
import ThePortfolio from "src/components/Portfolio.vue";
import TheContact from "src/components/Contact.vue";

export default defineComponent({
  name: "IndexPage",
  components: {
    Card,
    ThePortfolio,
    TheContact,
  },
  data() {
    return {
      receivedVariable: "", // Initialisez la valeur de receivedVariable
    };
  },
  methods: {
    handleVariableChangeB(value) {
      this.receivedVariable = value;
    },
  },
});
</script>
