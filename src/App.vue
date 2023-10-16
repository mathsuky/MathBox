<script lang="ts">
export default {
  name: 'App',
  data: () => ({
    drawer: false,
    navs: [
      {
        icon: 'mdi-home',
        title: 'HOME',
        link: '/'
      },
      {
        icon: 'mdi-home',
        title: 'ABOUT',
        link: '/about'
      }
    ]
  }),

}
</script>

<template>
  <v-app>
    <v-app-bar app color="blue" dark>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-app-bar-title>MathBox</v-app-bar-title>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list nav dense>
        <v-list-item v-for="nav in navs" :key="nav.title" :to="nav.link" exact>
          <v-list-item-title>{{ nav.title }}</v-list-item-title>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    

    <v-main> <router-view /></v-main>
  </v-app>
</template>
