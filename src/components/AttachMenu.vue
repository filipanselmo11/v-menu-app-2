<template>
  <v-menu
    :attach="localContainer"
    :close-on-click="false"
    v-model="menu"
    :position-x="x"
    :position-y="y">
    <v-list>
      <v-list-item>
        <v-list-item-content> Item 1 </v-list-item-content>
      </v-list-item>
      <!-- <v-list-item>
        <v-list-item-content> Item 2 </v-list-item-content>
      </v-list-item>
      <v-list-item>
        <v-list-item-content> Item 3 </v-list-item-content>
      </v-list-item> -->
    </v-list>
  </v-menu>
</template>

<script>
export default {
  name: "AttachMenu",
  props: {
    showMenu: {
      type: Boolean,
    },
    posX: {
      type: Number,
    },
    posY: {
      type: Number,
    },
    menuContainer: {
      type: String,
    },
  },
  data: () => ({
    localContainer: '',
    menu: false,
    x: 0,
    y: 0,
  }),
  methods:{},
  watch:{
    showMenu(val) {
        this.menu = val;
    },
    posX(val) {
        this.x = val;
    },
    posY(val) {
        this.y = val;
    },
    menuContainer(val) {
      this.localContainer = val;
    }
  },
};
</script>

<style>
</style>