<template>
  <div class="q-pa-md">
    <q-toolbar class="text-black">
      <!--
      <q-btn id="logo" round class="border-1" flat label="FB">
        <q-tooltip
          anchor="center left"
          self="center right"
          transition-show="scale"
          transition-hide="scale"
          class="bg-primary text-body2"
          >Florian BATT</q-tooltip
        >
      </q-btn>
        -->
      <q-space />

      <!--
        notice shrink property since we are placing it
        as child of QToolbar
      -->
      <q-tabs id="languages" class="" shrink>
        <!-- <q-tab name="What-I-do" label="What I do" no-caps />  
         <q-tab round name="About" label="About" no-caps />  -->
        <q-tab
          v-for="(value, key) in languages[selectedLanguage]"
          :key="key"
          class="language"
          :id="key"
          :name="key"
          :label="value"
          no-caps
          @click="changeLanguage(selectedLanguage)"
        />
      </q-tabs>
    </q-toolbar>
  </div>
</template>
<script>
import { reactive } from "vue";
import { ref } from "vue";
// import { defineComponent } from "vue";

export default {
  components: {},
  data() {
    return {};
  },
  setup() {
    let selectedLanguage = ref("FR"); // Par défaut, la langue sélectionnée est 'FR'
    const languages = reactive({
      FR: {
        language1: "Francais",
        language2: "Anglais",
      },
      EN: {
        language1: "French",
        language2: "English",
      },
    });
    function changeLanguage() {
      if (selectedLanguage.value == "FR") {
        selectedLanguage.value = "EN";
        console.log("EN :" + selectedLanguage.value);
      } else {
        selectedLanguage.value = "FR";
        console.log("FR :" + selectedLanguage.value);
      }
      return selectedLanguage;
    }

    return {
      selectedLanguage: changeLanguage(),
      languages,
      changeLanguage,
    };
  },
  mounted() {
    // Simule un clic sur l'onglet 'french'
    const frenchTab = document.querySelector("#languages");
    const firstLanguage = frenchTab.firstElementChild;
    const firstTab = firstLanguage.querySelector(".q-tab");
    console.log(firstTab);
    if (firstTab) {
      firstTab.click();
    }
  },
};
</script>
<style scoped>
#logo {
  border: solid 1px black;
}
</style>
