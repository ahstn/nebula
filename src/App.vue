<template>
  <v-app>
    <NavigationDrawer />
    <v-toolbar color="teal" dark prominent extended>
      <v-toolbar-side-icon></v-toolbar-side-icon>
      <v-toolbar-title>
        <span>DEPLOY</span>
        <span class="font-weight-light">BUNDLES</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>more_vert</v-icon>
      </v-btn>
    </v-toolbar>

    <v-layout row pb-2 class="grey lighten-4">
      <v-flex xs9 offset-xs2>
        <v-card class="card--flex-toolbar">
          <HelloWorld/>
        </v-card>
      </v-flex>
    </v-layout>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import NavigationDrawer from './components/NavigationDrawer'

export default {
  name: 'App',
  components: {
    HelloWorld,
    NavigationDrawer
  },
  data: () => ({ })
}
</script>

<style lang="stylus">
  .card--flex-toolbar
    margin-top: -64px

  .v-navigation-drawer
    margin-top: 128px!important
    width: 220px!important
    z-index: 0

  .v-navigation-drawer__border
    display: none
</style>
