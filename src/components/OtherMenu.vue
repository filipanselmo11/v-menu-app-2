<template>
  <div class="text-center">
    <v-menu :close-on-content-click="false" open-on-hover bottom offset-y>
      <template v-slot:activator="{ on }">
        <v-btn color="primary" dark v-on="on"> Dropdown </v-btn>
      </template>
      <v-list>
        <v-list-group
          v-for="item in items"
          :key="item.title"
          v-model="item.active"
        >
          <template v-slot:activator>
            <v-list-item>
              <v-list-item-content>
                <v-list-item-title>
                  {{ item.title }}
                </v-list-item-title>
              </v-list-item-content>
            </v-list-item>
          </template>
          <v-list v-for="subItem in item.items" :key="subItem.title">
            <v-list-item-content>
              <v-list-item-title>
                {{ subItem.title }}
              </v-list-item-title>
            </v-list-item-content>
          </v-list>
        </v-list-group>
      </v-list>
    </v-menu>
  </div>
</template>

<script>
export default {
  name: "OtherMenu",
  data: () => ({
    items: [
      {
        action: "local_activity",
        title: "Attractions",
        items: [{ title: "List Item" }],
      },
      {
        action: "restaurant",
        title: "Dinning",
        active: true,
        items: [
          { title: "Breakfast & brunch" },
          { title: "New American" },
          { title: "Sushi" },
        ],
      },
    ],
  }),
};
</script>

<style>
</style>