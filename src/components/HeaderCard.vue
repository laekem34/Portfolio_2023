<template>
  <div class="q-px-xs-md q-px-sm-lg q-px-sm-xl q-py-xs-sm q-py-sm-md" flat>
    <div class="row reverse-wrap q-px-xs-sm q-px-sm-xl q-py-xs-sm q-py-sm-md">
      <div class="col-12 col-sm-7">
        <div class="text-overline text-h1">test</div>
        <div
          id="title-header"
          class="wave-word text-h5 q-mt-sm q-mb-xs text-weight-bold"
        >
          <span>L</span>
          <span>o</span>
          <span>o</span>
          <span>k</span>
          <span>i</span>
          <span>n</span>
          <span>g</span>
          <span>&nbsp;</span>
          <span>f</span>
          <span>o</span>
          <span>r</span>
          <span>&nbsp;</span>
          <span>a</span>
          <span>n</span>
          <span>&nbsp;</span>
          <span>i</span>
          <span>n</span>
          <span>t</span>
          <span>e</span>
          <span>r</span>
          <span>n</span>
          <span>s</span>
          <span>h</span>
          <span>i</span>
          <span>p</span>
          <span>&nbsp;</span>
          <span id="as">a</span>
          <span>s</span>
          <span>&nbsp;</span>
          <span>W</span>
          <span>e</span>
          <span>b</span>
          <span>&nbsp;</span>
          <span>d</span>
          <span>e</span>
          <span>v</span>
          <span>e</span>
          <span>l</span>
          <span>o</span>
          <span>p</span>
          <span>e</span>
          <span>r</span>

          <!--Looking for an intership as Web developer-->
        </div>
        <div class="text-caption text-grey">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua.
        </div>
        <div class="row q-pa-md" style="">
          <div
            v-for="(link, i) in linksList[FR]"
            :key="i"
            class="col-xs-4 col-sm-3 col-md-2 col-xl-1 self-center"
          >
            <q-item-section class="q-pa-none" avatar>
              <a :href="link.link" target="_blank">
                <q-img
                  :src="require(`../assets/${link.icon}`)"
                  fit="contain"
                  class="self-center rounded-borders"
                  width="32px"
              /></a>
            </q-item-section>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-5 q-pb-lg q-pb-sm-none flex flex-center">
        <div class="pos" style="width: 150px; height: 150px">
          <img
            width="150"
            class="absolute"
            src="../assets/Photo-cv.png"
            style="
              position: absolute;
              top: 50%;
              left: 50%;
              transform: translate(-50%, -50%);
            "
          />
          <Vue3Lottie
            class="vue3-lottie"
            :animationData="AstronautJSON"
            :height="260"
            :width="260"
            :speed="0.25"
            style="
              position: absolute;
              top: 50%;
              left: 50%;
              transform: translate(-50%, -50%);
            "
          />
        </div>
      </div>
    </div>

    <div class="row q-pa-xs-sm q-pa-sm-xl q-py-xs-xl">
      <q-btn
        id="btn-portfolio"
        class="col-auto q-mr-lg"
        padding="xs md"
        outline
        color="primary"
        label="Portfolio"
        no-caps
      />
      <q-btn
        id="btn-talk"
        class="col-auto"
        padding="xs md"
        color="primary"
        label="Let's talk"
        no-caps
      />
    </div>
  </div>
</template>

<script>
import { Vue3Lottie } from "vue3-lottie";
import "vue3-lottie/dist/style.css";

import AstronautJSON from "../assets/Lottie-water.json";

import { reactive, onMounted } from "vue";

export default {
  components: {
    Vue3Lottie,
  },
  data() {
    return {
      AstronautJSON,
    };
  },
  setup() {
    const linksList = reactive([
      {
        title: "Bonjour, je suis Florian",
        caption: "quasar.dev",
        icon: "Linkedin.png",
        link: "https://www.linkedin.com/in/florian-batt/",
      },
    ]);

    onMounted(() => {
      const btnPortfolio = document.querySelector("#btn-portfolio");

      btnPortfolio.addEventListener("click", function () {
        scrollToPortfolio.call(this);
      });

      function scrollToPortfolio() {
        const portfolioElement = document.getElementById("portfolio");
        if (portfolioElement) {
          portfolioElement.scrollIntoView({ behavior: "smooth" });
        }
      }

      const btnTalk = document.querySelector("#btn-talk");

      btnTalk.addEventListener("click", function () {
        scrollToTalk.call(this);
      });

      function scrollToTalk() {
        const portfolioElement = document.getElementById("talk");
        if (portfolioElement) {
          portfolioElement.scrollIntoView({ behavior: "smooth" });
        }
      }

      const titreEl = document.querySelector("#title-header");

      setInterval(waveInt.bind(titreEl), 5000);

      function waveInt() {
        Array.from(this.childNodes)
          .filter((node) => node.nodeType === Node.ELEMENT_NODE)
          .forEach((element, index) => {
            setTimeout(() => {
              element.classList.add("wave");
            }, index * 50);
          });
        Array.from(this.childNodes)
          .filter((node) => node.nodeType === Node.ELEMENT_NODE)
          .forEach((node) => {
            if (node.classList.contains("wave")) {
              node.classList.remove("wave");
            }
          });
      }
    });

    return {
      linksList,
    };
  },
};
</script>

<style scoped>
.wave {
  animation-name: varfont;
  animation-duration: 1s;

  animation-iteration-count: 1;
}

.wave-word {
  font-family: "Roboto Flex";

  font-weight: 400;
  font-variation-settings: "YTLC" 493, "YTAS" 752, "YTDE" -201, "YTUC" 644,
    "YTFI" 674, "wght" 400;
}
@keyframes varfont {
  0% {
    font-variation-settings: "YTLC" 493, "YTAS" 752, "YTDE" -201, "YTUC" 644,
      "YTFI" 674, "wght" 400;
  }
  33% {
    font-variation-settings: "YTLC" 570, "YTAS" 854, "YTDE" -98, "YTUC" 760,
      "YTFI" 788, "wght" 400;
  }

  66% {
    font-variation-settings: "YTLC" 455, "YTAS" 700.5, "YTDE" -253, "YTUC" 586,
      "YTFI" 617, "wght" 400;
    /* font-variation-settings: "YTLC" 416, "YTAS" 649, "YTDE" -305, "YTUC" 528,
      "YTFI" 560, "wght" 400; */
  }
  100% {
    font-variation-settings: "YTLC" 493, "YTAS" 752, "YTDE" -201, "YTUC" 644,
      "YTFI" 674, "wght" 400;
  }
}
@media screen and (max-width: 900px) {
  #as:before {
    content: "\A";
    white-space: pre;
  }
}

.flex-center {
  display: flex;
  justify-content: center;
  align-items: center;
}
.pos {
  position: relative;
  width: 100%;
  height: 100%;
}
.pos img.absolute {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1;
}
.pos .vue3-lottie {
  position: absolute;
  top: 25%;
  left: 25%;
  z-index: 0;
}
</style>
