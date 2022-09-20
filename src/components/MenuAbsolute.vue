<template>
  <v-row justify="space-around">
    <v-col cols="12">
      <div>
        <v-row class="flex" justify="center">
          <v-card
            :ripple="false"
            class="portrait"
            img="https://placekitten.com/600/600"
            height="300px"
            width="300px"
            @click="show"
          ></v-card>
        </v-row>
        <v-menu
          v-model="showMenu"
          :position-x="x"
          :position-y="y"
          absolute
          offset-y
        >
          <v-list>
            <v-list-item v-for="(item, index) in items" :key="index">
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </div>
    </v-col>
  </v-row>
</template>
<script>
export default {
  name: "MenuAbsolute",
  data: () => ({
    showMenu: false,
    x: 0,
    y: 0,
    items: [
      { title: "Click Me" },
      { title: "Click Me 2" },
      { title: "Click Me 3" },
    ],
  }),
  methods: {
    show(e) {
      e.preventDefault;
      this.showMenu = false;
      this.x = e.clientX;
      this.y = e.clientY;
      console.log(this.x);
      console.log(this.y);
      this.$nextTick(() => {
        this.showMenu = true;
      });
    },
  },
};
</script>