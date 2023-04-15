<template>
  <div id="portfolio" class="q-pa-xs-md q-pa-md-xl">
    <!-- TODO 
Ajouter un effet de police qui grossi quand on descend le scroll
-->

    <h2
      id="title-h2"
      class="text-h1 text-center"
      style="font-family: 'RobotoFlex', sans-serif"
    >
      <span id="p">P</span>
      <span id="o">o</span>
      <span id="r">r</span>
      <span id="t">t</span>
      <span id="f">f</span>
      <span id="o_2">o</span>
      <span id="l">l</span>
      <span id="i">i</span>
      <span id="o_3">o</span>
    </h2>

    <SitePortfolio
      v-for="(links, index) in linksList"
      :key="index"
      :title="links.title"
      :text="links.text"
      :caption="links.caption"
      :icon="links.icon"
      :link="links.link"
      :image="links.image"
    />
  </div>
</template>

<script>
import { defineComponent, defineProps, reactive } from "vue";
import SitePortfolio from "src/components/SitePortfolio.vue";

export default defineComponent({
  name: "ThePortfolio",
  components: {
    SitePortfolio,
  },
  setup() {
    const linksList = reactive([
      {
        title: "Linking Platform",
        text: "This project is a linking platform to link with your neighboorhood, you can <strong>post</strong> and <strong>share</strong> share stuff, like other users and send <strong>messages</strong>.I made this project during my internship and got my DWWM degree presenting this website. The time to deliver beeing limited I used bootstrap for the style. I particulary enjoyed using Symfony 6, using the bundles and composants such as mailer, rate limiter. It also was really helpfull while dealing with unit tests.",
        caption: [
          "quasar.dev",
          "github.com/quasarframework",
          "chat.quasar.dev",
        ],
        icon: ["Symfony", "php", "JavaScript", "Bootstrap"],
        link: [
          "https://quasar.dev",
          "https://github.com/quasarframework",
          "https://chat.quasar.dev",
        ],
        image: "ask.png",
      },
      {
        title: "Portfolio",
        text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
        caption: [
          "quasar.dev",
          "github.com/quasarframework",
          "chat.quasar.dev",
        ],
        icon: ["Vue-js", "Quasar", "JavaScript"],
        link: [
          "https://quasar.dev",
          "https://github.com/quasarframework",
          "https://chat.quasar.dev",
        ],
        image: "portfolio.png",
      },
    ]);

    return {
      linksList,
    };
  },
  props: defineProps({
    linksList: {
      type: Array,
      required: true,
    },
  }),
  mounted() {
    // Récupère l'élément que l'on souhaite suivre
    const titleH2 = document.getElementById("title-h2");

    // Récupère la position de l'élément
    const elementPosition =
      titleH2.getBoundingClientRect().top + window.scrollY;

    // Calcule la position du milieu de l'écran
    const middleOfScreen = window.innerHeight / 2;

    // Calcule la position du quart de l'écran
    const quaterOfScreen = window.innerHeight / 4;

    // Calcule la position du quart de l'écran
    const threequaterOfScreen = middleOfScreen + quaterOfScreen;

    // Ajoute un événement de scroll sur la fenêtre
    window.addEventListener("load", () => {
      // Récupère la position actuelle de la fenêtre
      const currentScrollPosition = window.scrollY;

      // Calcule la position actuelle de l'élément par rapport au scroll
      const currentPosition = elementPosition - currentScrollPosition;

      // Calcule la position actuelle de l'élément en pourcentage par rapport à la position de l'écran visible
      const visiblePercentage =
        ((window.innerHeight - currentPosition) / window.innerHeight) * 100;
      monEvenement(visiblePercentage);
    });

    // Ajoute un événement de scroll sur la fenêtre
    window.addEventListener("scroll", () => {
      // Récupère la position actuelle de la fenêtre
      const currentScrollPosition = window.scrollY;

      // Calcule la position actuelle de l'élément par rapport au scroll
      const currentPosition = elementPosition - currentScrollPosition;

      // Calcule la position actuelle de l'élément en pourcentage par rapport à la position de l'écran visible
      const visiblePercentage =
        ((window.innerHeight - currentPosition) / window.innerHeight) * 100;

      // Vérifie si la position actuelle de l'élément est dans la zone du milieu de l'écran
      if (visiblePercentage > 0) {
        // L'élément se trouve au milieu de l'écran, déclenche l'événement
        monEvenement(visiblePercentage);
      }
    });

    function monEvenement(visiblePercentage) {
      // Code à exécuter lorsque l'élément est au milieu de l'écran
      const titleP = document.getElementById("p");
      const titleO = document.getElementById("o");
      const titleR = document.getElementById("r");
      const titleT = document.getElementById("t");
      const titleF = document.getElementById("f");
      const titleO2 = document.getElementById("o_2");
      const titleL = document.getElementById("l");
      const titleI = document.getElementById("i");
      const titleO3 = document.getElementById("o_3");
      // console.log(visiblePercentage * 8);
      // titleH2.style.opacity =
      //   Math.exp(Math.sqrt(visiblePercentage)) / Math.exp(Math.sqrt(100));
      const Maxlimite = 800;

      //EFFET CROISEMENT

      let shadowB = 0;
      shadowB = (titleH2.getBoundingClientRect().top - window.scrollY) / 50;
      let shadow2 = -shadowB;
      if (shadow2 > 0.4) {
        shadow2 = 0.4;
      }
      if (shadowB < -0.8) {
        shadowB = -0.8;
      }
      const widthOfScreen = window.innerWidth;
      // let letterSpacing = (widthOfScreen * 0.001 * fontPlus) / 60;
      let letterSpacing = widthOfScreen * 0.025;
      if (widthOfScreen) {
      }
      console.log("S:" + shadowB);
      titleH2.style.letterSpacing = letterSpacing + "px";
      // titleH2.style.letterSpacing = letterSpacing + "px";
      titleH2.style.textShadow =
        shadowB * 5 +
        "px " +
        shadowB +
        "px 0px white" +
        "," +
        shadow2 * 5 +
        "px " +
        shadow2 +
        "px 0px grey";
      titleH2.style.opacity = visiblePercentage / 20 - 1;
      //EFFET 3D
      // let fontPlus = 600;
      // let shadowB = 0;

      // if (visiblePercentage < 50) {
      //   console.log("<50");
      //   // fontPlus = 400 + visiblePercentage * 4;
      //   fontPlus = (visiblePercentage / 50) * (Maxlimite - 600) + 600;
      // } else {
      //   console.log("else");
      //   fontPlus = ((100 - visiblePercentage) / 50) * (Maxlimite - 600) + 600;
      // }
      // shadowB = (titleH2.getBoundingClientRect().top - window.scrollY) / 50;
      // let shadow2 = -shadowB;
      // const widthOfScreen = window.innerWidth;
      // // let letterSpacing = (widthOfScreen * 0.001 * fontPlus) / 60;
      // let letterSpacing = widthOfScreen * 0.025;
      // if (widthOfScreen) {
      // }
      // console.log(letterSpacing);
      // titleH2.style.letterSpacing = letterSpacing + "px";
      // // titleH2.style.letterSpacing = letterSpacing + "px";
      // titleH2.style.textShadow =
      //   shadowB / 4 +
      //   "px " +
      //   shadowB / 4 +
      //   "px 0px white" +
      //   "," +
      //   shadow2 / 4 +
      //   "px " +
      //   shadow2 / 4 +
      //   "px 0px grey";

      // titleP.style.fontWeight = fontPlus;
      // titleO.style.fontWeight = fontPlus;
      // titleR.style.fontWeight = fontPlus;
      // titleT.style.fontWeight = fontPlus;
      // titleF.style.fontWeight = fontPlus;
      // titleO2.style.fontWeight = fontPlus;
      // titleL.style.fontWeight = fontPlus;
      // titleI.style.fontWeight = fontPlus;
      // titleO3.style.fontWeight = fontPlus;
    }
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

h2 {
  animation-duration: 3s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
  animation-name: anim-weiht;
}
@keyframes anim-weight {
  0% {
    font-weight: 400;
  }
  100% {
    font-weight: 500;
  }
  0% {
    font-weight: 400;
  }
}
#title-h2 {
  font-size: 5em;
  color: rgba(255, 255, 255, 0);
}
</style>
