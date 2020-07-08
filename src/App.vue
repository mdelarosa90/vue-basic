<template>
  <v-app>
    <v-card color="blue lighten-4" tile>
      <!-- <v-toolbar dense color="blue" dark app>
        <v-app-bar-nav-icon @click="showDrawer"></v-app-bar-nav-icon>
        <v-toolbar-title>Vuetify</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn color="success">Ingreso</v-btn>
      </v-toolbar> -->
      <v-app-bar dense color="blue" dark>
        <v-app-bar-nav-icon @click="showDrawer"></v-app-bar-nav-icon>
        <v-toolbar-title>Vuetify</v-toolbar-title>
        <v-spacer></v-spacer>
        <v-btn color="success">Ingreso</v-btn>
      </v-app-bar>

    </v-card>
    <v-navigation-drawer app v-model="drawer" temporary>
      <v-layout mt-4 column align-center>
        <v-flex>
          <v-list-item-avatar>
                <v-img src="https://randomuser.me/api/portraits/women/85.jpg"></v-img>
              </v-list-item-avatar>
        </v-flex>
        <v-flex>
          <p>Juanito Perez</p>
        </v-flex>
      </v-layout>
      <v-layout>
        <v-flex>
          <v-btn color="success" text block :to="{name: 'Home'}">Home</v-btn>
           <v-btn color="success" text block :to="{name: 'Tareas'}">Lista de Tareas</v-btn>
        </v-flex>
      </v-layout>
    </v-navigation-drawer>

    <v-main>
      <router-view></router-view>
    </v-main>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    //HelloWorld,
  },
  methods: {
    showDrawer() {
      this.drawer = !this.drawer
    }
  },
  data: () => ({
    //
    drawer: false,
  }),
};
</script>
