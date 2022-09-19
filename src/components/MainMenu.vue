<template>
  <div>
    <template v-for="item in items">
      <v-hover :key="item.id" close-delay="200" open-delay="200">
        <v-btn
          v-if="item.children"
          flat
          slot-scope="{ hover }"
          style="position: relative"
          :ripple="false"
        >
          Item {{ item.id }}
          <nested-menu :items="items" v-if="hover"></nested-menu>
        </v-btn>
        <v-btn v-else flat> Item {{ item.id }} </v-btn>
      </v-hover>
    </template>
  </div>
</template>

<script>
import NestedMenu from "./NestedMenu.vue";
export default {
  components: { NestedMenu },
  data: () => ({
    items: [
      {
        id: "1",
        children: [
          {
            id: "2",
            children: [
              {
                id: "3",
                children: [
                  {
                    id: "4",
                    children: [
                      {
                        id: "5",
                      },
                    ],
                  },
                ],
              },
            ],
          },
          {
            id: "6",
            children: [
              {
                id: "7",
              },
              {
                id: "8",
              },
              {
                id: "9",
              },
            ],
          },
          {
            id: "10",
            children: [
              {
                id: "11",
              },
              {
                id: "12",
              },
            ],
          },
          {
            id: "13",
            children: [
              {
                id: "14",
              },
              {
                id: "15",
              },
            ],
          },
          {
            id: "16",
            children: [
              {
                id: "17",
              },
              {
                id: "18",
              },
            ],
          },
          {
            id: "19",
            children: [
              {
                id: "20",
              },
              {
                id: "21",
              },
            ],
          },
        ],
      },

      {
        id: "22",
        children: [
          {
            id: "23",
            children: [
              {
                id: "24",
              },
              {
                id: "25",
              },
              {
                id: "26",
              },
              {
                id: "27",
              },
              {
                id: "28",
              },
            ],
          },
          {
            id: "29",
          },
          {
            id: "30",
          },
        ],
      },
      {
        id: "31",
      },
      {
        id: "32",
      },
      {
        id: "33",
      },
    ],
  }),
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
    height: 24px !important;
}
</style>