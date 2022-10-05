<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <div class="d-flex align-center">
        <v-img
          alt="Vuetify Logo"
          class="shrink mr-2"
          contain
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-logo-dark.png"
          transition="scale-transition"
          width="40"
        />

        <v-img
          alt="Vuetify Name"
          class="shrink mt-1 hidden-sm-and-down"
          contain
          min-width="100"
          src="https://cdn.vuetifyjs.com/images/logos/vuetify-name-dark.png"
          width="100"
        />
      </div>

      <v-spacer></v-spacer>

      <v-btn
        href="https://github.com/vuetifyjs/vuetify/releases/latest"
        target="_blank"
        text
      >
        <span class="mr-2">Latest Release</span>
        <v-icon>mdi-open-in-new</v-icon>
      </v-btn>
    </v-app-bar>

    <br />

    <v-main>
      <!-- <menu-final></menu-final> -->
      <!-- <menu-absolute></menu-absolute> -->
      <!-- <menu-1></menu-1> -->
      <!-- <container-menu></container-menu> -->
      <html-menu></html-menu>
    </v-main>
  </v-app>
</template>

<script>
// import MenuFinal from './components/MenuFinal.vue';
// import AbsoluteMenu from './components/AbsoluteMenu.vue';
// import Menu1 from './components/Menu1.vue';
// import MenuAbsolute from './components/MenuAbsolute.vue';

// import ContainerMenu from "./components/ContainerMenu.vue"
import HtmlMenu from './components/HtmlMenu.vue';

// import MenuComponent from './components/MenuComponent.vue';
export default {
  components: { HtmlMenu },
  name: "App",
  data: () => ({
    //
  }),
};
</script>
