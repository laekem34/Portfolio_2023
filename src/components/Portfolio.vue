<template>
  <div class="q-pa-xs-md q-pa-md-xl">
    <h2 class="text-h5 text-weight-bold text-white">Portfolio</h2>
    <SitePortfolio
      v-for="(links, index) in linksList"
      :key="index"
      :title="links.title"
      :text="links.text"
      :caption="links.caption"
      :icon="links.icon"
      :link="links.link"
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
        icon: ["Symfony-icon.png", "Bootstrap-icon.png", "JavaScript-icon.png"],
        link: [
          "https://quasar.dev",
          "https://github.com/quasarframework",
          "https://chat.quasar.dev",
        ],
      },
      {
        title: "Futur Project",
        text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
        caption: [
          "quasar.dev",
          "github.com/quasarframework",
          "chat.quasar.dev",
        ],
        icon: ["JavaScript-icon.png", "Bootstrap-icon.png", "Symfony-icon.png"],
        link: [
          "https://quasar.dev",
          "https://github.com/quasarframework",
          "https://chat.quasar.dev",
        ],
      },
      {
        title: "Futur Project 2",
        text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
        caption: [
          "quasar.dev",
          "github.com/quasarframework",
          "chat.quasar.dev",
        ],
        icon: ["Bootstrap-icon.png", "JavaScript-icon.png", "Symfony-icon.png"],
        link: [
          "https://quasar.dev",
          "https://github.com/quasarframework",
          "https://chat.quasar.dev",
        ],
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
