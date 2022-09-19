<template>
  <v-list dense class="nested-menu">
    <v-hover
      v-for="item in items"
      :key="item.id"
      close-delay="200"
      open-delay="200"
    >
      <v-list v-if="item.children" slot-scope="{ hover }">
        <v-list-item-title> Item {{ item.id }} </v-list-item-title>
        <v-list-item-action class="justify-end">
          <v-icon>mdi-arrow</v-icon>
        </v-list-item-action>
        <nested-menu v-if="hover" :items="item.children"></nested-menu>
      </v-list>
      <v-list v-else v-ripple>
        <v-list-item-title> Item {{ item.id }} </v-list-item-title>
      </v-list>
    </v-hover>
  </v-list>
</template>

<script>
export default {
  name: "NestedMenu",
  components: { NestedMenu: () => import("./NestedMenu.vue") },
  props: ["items"],
};
</script>

<style scoped>
::v-deep .v-btn__content {
  position: relative !important;
}

::v-deep .v-list {
  position: relative !important;
}

::v-deep .v-list--dense .v-list:not(.v-list--avatar) {
  height: 28px !important;
}

::v-deep .v-list__action {
  min-width: 32px !important;
}

.nested-menu {
  z-index: 999;
  position: absolute;
  bottom: calc(100% + 8px);
  left: -16px;
  border: 2px solid darkgrey;
  height: fit-content;
  top: 0;
  right: initial;
  left: 10%;
}
</style>