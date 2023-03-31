<template>
  <q-card
    class="my-card q-px-xs-md q-px-sm-lg q-px-sm-xl q-py-xs-sm q-py-sm-md"
    flat
  >
    <div class="row reverse-wrap q-px-xs-sm q-px-sm-xl q-py-xs-sm q-py-sm-md">
      <div class="col-12 col-sm-7">
        <div class="text-overline text-h1">Hello, I'm Florian</div>
        <div class="text-h5 q-mt-sm q-mb-xs text-weight-bold">
          Looking for an intership as Web developer
        </div>
        <div class="text-caption text-grey">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua.
        </div>
        <div class="row">
          <div
            v-for="link in linksList"
            :key="link.title"
            v-bind="link"
            class="col-xs-4 col-sm-3 col-md-2 col-xl-1"
          >
            <q-item
              class="justify-center"
              clickable
              tag="a"
              target="_blank"
              :href="link.link"
            >
              <q-item-section v-if="link.icon" class="q-pa-none" avatar>
                <q-icon class="self-center" :name="link.icon" />
              </q-item-section>
            </q-item>
          </div>
        </div>
      </div>

      <div class="col-12 col-sm-5 flex flex-center">
        <q-avatar size="150px">
          <img src="https://cdn.quasar.dev/img/parallax2.jpg" />
        </q-avatar>
      </div>
    </div>

    <div class="row q-pa-xs-sm q-pa-sm-xl q-py-xs-xl">
      <q-btn
        class="col-auto q-mr-lg"
        padding="xs md"
        outline
        color="primary"
        label="Portfolio"
        no-caps
      />
      <q-btn
        class="col-auto"
        padding="xs md"
        color="primary"
        label="Let's talk"
        no-caps
      />
    </div>
  </q-card>
</template>

<script>
import { reactive } from "vue";
export default {
  setup() {
    const linksList = reactive([
      {
        title: "Docs",
        caption: "quasar.dev",
        icon: "school",
        link: "https://quasar.dev",
      },
      {
        title: "Github",
        caption: "github.com/quasarframework",
        icon: "code",
        link: "https://github.com/quasarframework",
      },
      {
        title: "Discord Chat Channel",
        caption: "chat.quasar.dev",
        icon: "chat",
        link: "https://chat.quasar.dev",
      },
    ]);

    return {
      linksList,
    };
  },
};
</script>

<style scoped></style>
