<!-- <template>
  <q-layout
    class="card bg-white text-black shadow-10 rounded-border-30 q-mb-xl"
  >
    <div
      class="my-card q-px-xs-md q-px-sm-lg q-px-sm-xl q-py-xs-lg q-py-sm-xl"
      flat
    >
      <div class="row wrap" v-if="$q.screen.width >= 800">
        <div class="left col-7">
          <div class="row wrap q-pl-xs-sm q-pl-sm-xl" style="height: 100%">
            <div class="text col-12">
              <div class="row q-pb-lg">
                <div class="col-auto text-subtitle1 text-weight-bold q-mt-md">
                  <span>{{ title }} </span>
                </div>
                <div class="col-7">
                  <div class="row justify-start" style="height: 100%">
                    <div
                      v-for="(link, i) in link"
                      :key="i"
                      class="col-xs-4 col-sm-3 col-md-2 col-xl-1 self-center"
                    >
                      <q-item-section v-if="icon[i]" class="q-pa-none" avatar>
                        <q-img
                          :src="require(`../assets/${icon[i]}`)"
                          fit="contain"
                          class="self-center rounded-borders"
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
            <div class="button col-12 self-end q-pt-xs-lg">
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

        <div class="right col-5 flex flex-center q-pl-lg q-pt-lg">
          <q-img
            src="https://cdn.quasar.dev/img/parallax2.jpg"
            fit="cover"
            style="max-width: 400px; max-height: 300px"
            class="rounded-borders"
          ></q-img>
        </div>
      </div> -->

<!-- ELSE -->

<!-- <div class="row wrap" v-if="$q.screen.width <= 800">
        <div class="left col-12">
          <div class="row wrap q-pl-xs-sm q-pl-sm-xl" style="height: 100%">
            <div class="text col-12">
              <div class="row q-pb-lg">
                <div class="col-auto text-subtitle1 text-weight-bold q-mt-md">
                  <span>{{ title }} </span>
                </div>
                <div class="col-7">
                  <div class="row" style="height: 100%">
                    <div
                      v-for="(link, i) in link"
                      :key="i"
                      class="col-xs-4 col-sm-3 col-md-2 col-xl-1 self-center"
                    >
                      <q-item-section v-if="icon[i]" class="q-pa-none" avatar>
                        <q-img
                          :src="require(`../assets/${icon[i]}`)"
                          fit="contain"
                          class="self-center rounded-borders"
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
            <div
              id="img"
              class="right col-12 flex flex-center q-pl-lg-lg q-pt-lg"
            >
              <q-img
                src="https://cdn.quasar.dev/img/parallax2.jpg"
                fit="cover"
                style="max-width: 400px; max-height: 300px"
                class="rounded-borders"
              ></q-img>
            </div>
            <div class="button col-12 self-end q-pt-xs-lg">
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
      </div>
    </div>
  </q-layout>
</template> -->

<template>
  <q-layout
    class="card bg-white text-black shadow-10 rounded-border-30 q-mb-xl"
  >
    <div
      class="my-card q-px-xs-md q-px-sm-lg q-px-sm-xl q-py-xs-lg q-py-sm-xl"
      flat
    >
      <div id="group" class="row wrap">
        <div class="left col-12 col-md-7">
          <div
            id="test"
            class="row wrap justify-center q-pl-xs-sm q-pl-sm-xl"
            style="height: 100%"
          >
            <div class="text col-12">
              <div class="row q-pb-lg">
                <div class="col-auto text-subtitle1 text-weight-bold q-mt-md">
                  <span>{{ title }} </span>
                  <p>{{ receivedVariable }}</p>
                </div>
                <div class="col-7">
                  <div class="row justify-start" style="height: 100%">
                    <div
                      v-for="(icons, i) in icon"
                      :key="i"
                      class="col-2 col-lg-1 self-center"
                    >
                      <q-item-section v-if="icon[i]" class="q-pa-none" avatar>
                        <q-img
                          :src="require(`../assets/${icon[i]}.png`)"
                          fit="contain"
                          class="self-center rounded-borders"
                          width="24px"
                        />
                        <q-tooltip class="text-body2">{{ icon[i] }}</q-tooltip>
                      </q-item-section>
                    </div>
                  </div>
                </div>
              </div>
              <div class="text-body2">
                <span v-html="text"></span>
              </div>
            </div>
            <div id="btn" class="button col-12 self-end q-pt-xs-lg">
              <q-btn
                :href="link"
                target="_blank"
                padding="xs md"
                outline
                color="primary"
                label="Consulter"
                no-caps
              />
            </div>
          </div>
        </div>

        <div
          id="img"
          class="right col-12 col-md-5 flex flex-center q-pl-md-lg q-pt-lg"
        >
          <q-img
            :src="require(`../assets/${image}`)"
            fit="cover"
            style="width: 100%"
            class="rounded-borders"
          ></q-img>
        </div>
      </div>
    </div>
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
    image: {
      type: Array,
      required: true,
    },
    receivedVariable: {
      type: String,
      required: true,
    },
  },
  mounted() {
    //this.moveRightElement();
    let img = document.getElementById("img");
    let btn = document.getElementById("btn");
    let test = document.getElementById("test");
    let group = document.getElementById("group");

    // console.log(window.innerWidth);
    window.addEventListener("load", function () {
      window.dispatchEvent(new Event("resize"));
    });

    window.onresize = function () {
      if (window.innerWidth < 1024) {
        test.insertBefore(img, btn);
      } else {
        group.appendChild(img);
      }
    };
  },
  methods: {},
});
</script>

<style scoped></style>
