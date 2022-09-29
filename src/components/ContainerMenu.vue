<template>
  <v-container class="fill-height" @click="onClick">
    <div
      id="meu-container"
      style="
        width: 500px;
        height: 356px;
        border: 3px solid blue;
        position: relative;
      "
    >
      <span style="position: absolute; bottom: 0; right: 0">
        x: {{ x }}, y: {{ y }}
      </span>
    </div>
    <attach-menu
      :menuContainer="menuContainer"
      :showMenu="menu"
      :posX="x"
      :posY="y"
    ></attach-menu>
  </v-container>
</template>

<script>
import AttachMenu from "./AttachMenu.vue";
export default {
  components: { AttachMenu },
  name: "ContainerMenu",
  data: () => ({
    menu: false,
    menuContainer: 'meu-container',
    x: 0,
    y: 0,
  }),
  methods: {
    onClick(e) {
      this.menu = false;
      e.clientX = 489.5;
      e.clientY = 292;
      this.x = e.clientX;
      this.y = e.clientY;
    //   console.log(e);
    //   const container = document.getElementById(this.menuContainer);
    //   const bounds = container.getBoundingClientRect();
    //   const x = e.clientX - bounds.left;
    //   const y = e.clientY - bounds.top;
    //   if (x < 0 || y < 0 || x > 900 || y > 900) {
    //     alert("Por favor, clique dentro da caixa azul");
    //     return;
    //   }
    //   this.x = x;
    //   this.y = y;
      this.$nextTick(() => (this.menu = true));
    },
  },
};
</script>

<style>
</style>