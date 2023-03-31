<template>
  <q-layout
    class="card bg-white text-black shadow-10 rounded-border-30 q-mb-xl"
  >
    <q-card
      class="my-card q-px-xs-md q-px-sm-lg q-px-sm-xl q-py-xs-lg q-py-sm-xl"
      flat
    >
      <div class="row wrap">
        <div class="col-7">
          <div class="row wrap q-pl-xs-sm q-pl-sm-xl" style="height: 100%">
            <div class="col-12">
              <div class="row q-pb-lg">
                <div class="col-auto text-subtitle1 text-weight-bold q-mt-md">
                  <span>{{ title }} </span>
                </div>
                <div class="col-7">
                  <div class="row justify-center" style="height: 100%">
                    <div
                      v-for="(link, i) in link"
                      :key="i"
                      class="col-xs-4 col-sm-3 col-md-2 col-xl-1 self-center"
                    >
                      <q-item-section v-if="icon[i]" class="q-pa-none" avatar>
                        <q-img
                          :src="require(`../assets/${icon[i]}`)"
                          fit="contain"
                          class="justify-center rounded-borders"
                          width="20px"
                        />
                      </q-item-section>
                    </div>
                  </div>
                </div>
              </div>
              <div class="text-body2">
                <span v-html="text"></span>
              </div>
            </div>
            <div class="col-12 self-end q-pt-xs-lg">
              <q-btn
                padding="xs md"
                outline
                color="primary"
                label="Look"
                no-caps
              />
            </div>
          </div>
        </div>

        <div class="col-5 flex flex-center q-pl-lg q-pt-lg">
          <q-img
            src="https://cdn.quasar.dev/img/parallax2.jpg"
            fit="cover"
            style="max-width: 400px; max-height: 300px"
            class="rounded-borders"
          ></q-img>
        </div>
      </div>
    </q-card>
  </q-layout>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    title: {
      type: String,
      required: true,
    },
    text: {
      type: Array,
      required: true,
    },
    caption: {
      type: Array,
      required: true,
    },
    icon: {
      type: Array,
      required: true,
    },
    link: {
      type: Array,
      required: true,
    },
  },
});
</script>

<style scoped></style>
