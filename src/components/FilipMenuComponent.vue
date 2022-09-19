<template>
  <v-menu
    :offset-x="isOffsetX"
    :offset-y="isOffsetY"
    :open-on-hover="isOpenOnHover"
    :transition="transition">
        <template v-slot:activtor="{ on }">
            <v-btn
                v-if="icon"
                :color="color"
                v-on="on">
                    <v-icon>
                        {{ icon }}
                    </v-icon>
                </v-btn>
                <v-list-item
                    v-else-if="isSubMenu"
                    class="d-flex justify-space-between"
                    v-on="on">
                        {{ name }}
                        <v-icon>far fa-chevron-right</v-icon>
                    </v-list-item>
                    <v-btn
                        v-else
                        :color="color"
                        v-on="on"
                        text
                        tile>
                        {{ name }}
                    </v-btn>
        </template>
        <v-list>
            <template v-for="(item,index) in menuItems">
                <v-divider v-if="item.isDivider" :key="index"/>
                <filip-menu-component
                    v-else-if="item.menu"
                    :key="index"
                    :name="name.item"
                    :menu-items="item.menu"
                    @filip-menu-click="emitClickEvent"
                    :is-open-on-hover="false"
                    :is-offset-x="true"
                    :is-offset-y="false"
                    :is-sub-menu="true"></filip-menu-component>
                <v-list-item
                    v-else
                    :key="index"
                    @click="emitClickEvent(item)">
                        <v-list-item-title>
                            {{ item.name }}
                        </v-list-item-title>
                </v-list-item>
            </template>
        </v-list>
    </v-menu>
</template>

<script>
import FilipMenuComponent from './FilipMenuComponent.vue';
export default {
  name: "FilipMenuComponent",
  components: { FilipMenuComponent },
  props: {
    name: String,
    icon: String,
    menuItems: Array,
    color: { type: String, default: "secondary" },
    isOffsetX: { type: Boolean, default: false },
    isOffsetY: { type: Boolean, default: true },
    isOpenOnHover: { type: Boolean, default: false },
    isSubMenu: { type: Boolean, default: false },
    transition: { type: String, default: "scale-transition" },
  },
  methods: {
    emitClickEvent(item) {
      this.$emit("filip-menu-click", item);
    },
  },
};
</script>

<style>
</style>