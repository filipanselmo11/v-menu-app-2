<template>
   <v-container>
        <v-dialog v-model="dialog"
                  fullscreen
                  content-class="my-dialog">
          <v-btn slot="activator">Open dialog</v-btn>
          <v-card flat>
            <v-toolbar dark color="primary">
              <v-toolbar-title>Dialog</v-toolbar-title>
              <v-spacer></v-spacer>
              <v-btn icon dark @click.native="dialog = false">
                <v-icon>close</v-icon>
              </v-btn>
            </v-toolbar>
            <v-card-text>
              <div style="height:100px">
                <div class="wrapper">
             <v-select                       :items="['Item 1', 'Item 2']"
                  v-model="selectedItem"
                  label="Select item"
                  attach></v-select>
                </div>
              <div style="height:600px"></div>
            </v-card-text>
          </v-card>
        </v-dialog>
      </v-container>
</template>

<script>
export default {
  name: "MenuComponent",
  data: () => ({
    dialog: false,
    selectedItem: null,
  }),
};
</script>

<style scoped>
.wrapper {
  height: 60px;
  overflow: hidden;
  border: 1px solid black;
}
</style>