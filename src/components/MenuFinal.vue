<template>
    <categorie-menu
        :name="name"
        :menuItems="fileMenuItems"
        @sub-menu-click="onMenuItemClick"></categorie-menu>
</template>

<script>
const { default: CategorieMenu }=require("./CategorieMenu.vue");

export default {
  name: "MenuFinal",
  components: { CategorieMenu },
  data: () => ({
    name: 'New Menu',
    fileMenuItems: [
      {
        name: "Menu Item 1",
        action: () => {
          console.log("menu-item-1");
        },
      },
      { isDivider: true },
      { name: "Menu Item 2" },
      {
        name: "Sub 1",
        menu: [
          { name: "1.1" },
          { name: "1.2" },
          {
            name: "Sub-menu 2",
            menu: [
              { name: "2.1" },
              { name: "2.2" },
              {
                name: "Sub-menu 3",
                menu: [
                  { name: "3.1" },
                  { name: "3.2" },
                  {
                    name: "Sub-menu 4",
                    menu: [{ name: "4.1" }, { name: "4.2" }, { name: "4.3" }],
                  },
                ],
              },
            ],
          },
        ],
      },

      { name: "Menu Item 3" },
      { isDivider: true },
      {
        name: "Menu Item 4",
        action: () => {
          console.log("menu-item-4");
        },
      },
      {
        name: "Menu Item 5",
        action: () => {
          console.log("menu-item-5");
        },
      },
    ],
  }),
  methods: {
    onMenuItemClick(item) {
        console.log(`onMenuItemClick(), item=${item}`);
    }
  },
};
</script>

<style>
</style>