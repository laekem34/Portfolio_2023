<template>
  <div class="q-pa-md">
    <q-toolbar class="text-black">
      <q-btn id="logo" round class="border-1" flat label="FB" />
      <q-space />

      <!--
        notice shrink property since we are placing it
        as child of QToolbar
      -->
      <q-tabs shrink>
        <q-tab round name="About" label="About" no-caps />
        <q-tab name="What-I-do" label="What I do" no-caps />
        <q-tab name="Portfolio" label="Portfolio" no-caps />
        <q-tab name="Let-s-talk" label="Let's talk" no-caps />
      </q-tabs>
    </q-toolbar>
  </div>
</template>

<style scoped>
#logo {
  border: solid 1px black;
}
</style>
