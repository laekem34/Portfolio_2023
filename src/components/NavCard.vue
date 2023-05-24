<template>
  <div class="q-pa-md">
    <q-toolbar class="text-black">
      <a href="https://www.epsi.fr">
        <q-img q-m-lg style="width: 24px" src="../assets/Epsi.png" />
        <span style="font-size: 16px">&nbsp;epsi&nbsp;</span>
        <span style="font-size: 10px"
          >&nbsp;école d'ingénierie informatique</span
        >
      </a>

      <q-space />

      <q-tabs id="languages" class="" shrink>
        <!-- <q-tab name="What-I-do" label="What I do" no-caps />  
        
        <q-tab round name="About" label="About" no-caps /> 




        Working on FR & EN for next version
        -->

        <q-tab
          v-for="(value, key) in languages[selectedLanguage]"
          :key="key"
          class="language"
          :id="key"
          :name="key"
          :label="value"
          no-caps
          @click="passVariableToParent(value)"
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
    function changeLanguage(lang) {
      console.log(lang);
      if (lang == "Francais" || lang == "French") {
        selectedLanguage.value = "FR";
        console.log("selectedLanguage :" + selectedLanguage.value);
      } else {
        selectedLanguage.value = "EN";
        console.log("selectedLanguage :" + selectedLanguage.value);
      }
      return selectedLanguage;
    }

    return {
      selectedLanguage: changeLanguage(),
      languages,
      changeLanguage,
    };
  },
  methods: {
    passVariableToParent(lang) {
      console.log("pass");
      const variable = this.changeLanguage(lang);
      this.$emit("variable-changed", variable);
    },
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
