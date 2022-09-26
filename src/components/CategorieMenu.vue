<template>
  <v-menu
    :close-on-content-click="false"
    :offset-x="isOffsetX"
    :offset-y="isOffsetY"
    :open-on-hover="isOpenOnHover"
    :transition="transition"
    :value="openMenu"
    v-model="menuOpened"
  >
    <template v-slot:activator="{ on }">
      <v-btn :color="color" v-if="icon" v-on="on">
        <v-icon>
          {{ icon }}
        </v-icon>
      </v-btn>
      <v-list-item
        class="d-flex justify-space-between"
        v-else-if="isSubMenu"
        v-on="on"
      >
        {{ name }}
        <div class="flex-grow-1"></div>
        <v-icon> mdi-chevron-right </v-icon>
      </v-list-item>
      <v-btn :color="color" @click="openMenu = true" text v-else v-on="on">
        {{ name }}
      </v-btn>
    </template>
    <v-list>
      <template v-for="(item, index) in menuItems">
        <v-divider :key="index" v-if="item.isDivider" />
        <categorie-menu
          :is-offset-x="true"
          :is-offset-y="false"
          :is-open-on-hover="false"
          :is-sub-menu="true"
          :key="index"
          :menu-items="item.menu"
          :name="item.name"
          @sub-menu-click="emitClickEvent"
          v-else-if="item.menu"
        ></categorie-menu>
        <v-list-item
          :key="index"
          @click="emitClickEvent(item)"
          v-else
        ></v-list-item>
        <v-list-item-action :key="index" v-if="item.action">
            <v-icon>
                mdi-{{ item.icon }}
            </v-icon>
        </v-list-item-action>
        <v-list-item-title :key="index">
            {{ item.name }}
        </v-list-item-title>
      </template>
    </v-list>
  </v-menu>
</template>

<script>
export default {
  name: "CategorieMenu",
  props: {
    name: String,
    icon: String,
    menuItems: Array,
    color: { type: String, default: "secondary" },
    isOffsetX: { type: Boolean, default: false },
    isOffsetY: { type: Boolean, default: true },
    isSubMenu: { type: Boolean, default: false },
    transition: { type: String, default: "scale-transition" },
  },
  data: () => ({
    openMenu: false,
    isOpenOnHover: true,
    menuOpened: false,
  }),
  methods: {
    emitClickEvent(item) {
      this.$emit("sub-menu-click", item);
      this.openMenu = false;
      this.menuOpened = false;
    },
  },
  watch: {
    menuOpened() {
      this.isOpenOnHover = !this.menuOpened;
    },
  },
};
</script>

<style>
</style>