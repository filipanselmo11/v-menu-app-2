<template>
  <div class="text-center">
    <v-container>
      <v-menu offset-y>
        <template v-slot:activator="{ on, attrs }">
          <v-btn primary dark v-on="on" v-bind="attrs"> Dropdown </v-btn>
        </template>
        <v-list dense>
          <v-list-item v-for="i in 4" :key="i">
            <v-list-item-title>{{ i }}</v-list-item-title>
          </v-list-item>

          <v-menu offset-x open-on-hover>
            <template v-slot:activator="{ on, attrs }">
              <v-list-item v-on="on" v-bind="attrs">
                <v-list-item-title>Open SubMenu</v-list-item-title>
              </v-list-item>
            </template>
            <v-list dense>
              <v-list-item v-for="i in 5" :key="i">
                <v-list-item-title>{{ i }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>

          <v-list-item v-for="i in 5" :key="i">
            <v-list-item-title>{{ i + 5 }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-container>
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>