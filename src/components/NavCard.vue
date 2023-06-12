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

      <q-tabs id="languages" class="" shrink :model-value="locale">
        <!-- <q-tab name="What-I-do" label="What I do" no-caps />  
        
        <q-tab round name="About" label="About" no-caps /> 




        Working on FR & EN for next version
        -->

        <q-tab
          v-for="(value, key) in languages"
          :key="key"
          class="language"
          :id="key"
          :name="key"
          :label="value[locale]"
          no-caps
          @click="changeLanguage(key)"
        />
      </q-tabs>
    </q-toolbar>
  </div>
</template>
<script>
import { reactive } from "vue";
import { ref, getCurrentInstance, computed, inject } from "vue";

export default {
  components: {},
  data() {
    return {};
  },
  setup() {
    const instance = getCurrentInstance()
    const locale = inject('locale')
    const languages = reactive({
      FR: {
        FR: "Francais",
        EN: "French",
      },
      EN: {
        FR: "Anglais",
        EN: "English",
      },
    });

    function changeLanguage(lang) {
      instance.root.ctx.setLocale(lang)

      // Voir App.vue

      // Ici la la fonction changeLanguage va faire remonter le changement au premier Composant App.vue
      
      // La réactivité se fait dans tous les composants ou tu demande la valeur

      // const locale = inject('locale') // FR ou EN

      // if (lang == "Francais" || lang == "French") {
      //   selectedLanguage.value = "FR";
      //   console.log("selectedLanguage :" + selectedLanguage.value);
      // } else {
      //   selectedLanguage.value = "EN";
      //   console.log("selectedLanguage :" + selectedLanguage.value);
      // }
      // return selectedLanguage;
    }

    return {
      //selectedLanguage, : changeLanguage(),
      languages,
      locale,
      changeLanguage,
    };
  },
  methods: {
    // Plus besoin de faire remonter l'info

    // passVariableToParent(lang) {
    //   console.log("pass");
    //   const variable = this.changeLanguage(lang);
    //   this.$emit("variable-changed", variable);
    // },
  },
  mounted() {
    // :model-value="locale" sur le qtabs va dire quel est l'onglet sélectioné de base pour ne pas avoir a simuler un click

    // Simule un clic sur l'onglet 'french'
    // const frenchTab = document.querySelector("#languages");
    // const firstLanguage = frenchTab.firstElementChild;
    // const firstTab = firstLanguage.querySelector(".q-tab");
    // console.log(firstTab);
    // if (firstTab) {
    //   firstTab.click();
    // }
  },
};
</script>
<style scoped>
#logo {
  border: solid 1px black;
}
</style>
