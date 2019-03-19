<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      fixed
      clipped
      class="grey lighten-4"
      app
    >
      <v-list
        dense
        class="grey lighten-4"
      >
        <template v-for="(item, i) in items">
          <v-layout
            v-if="item.heading"
            :key="i"
            row
            align-center
          >
            <v-flex xs6>
              <v-subheader v-if="item.heading">
                {{ item.heading }}
              </v-subheader>
            </v-flex>
          </v-layout>
          <v-divider v-else-if="item.divider" :key="i" dark class="my-3" />
          <v-list-tile v-else :key="i">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title class="grey--text">
                {{ item.text }}
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </template>
      </v-list>
    </v-navigation-drawer>

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

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data: () => ({
    items: [
        { heading: 'Cluster' },
        { icon: 'add', text: 'Deployments' },
        { icon: 'touch_app', text: 'Builder' },
        { icon: 'help', text: 'Visualiser' },
        { divider: true },
        { icon: 'settings', text: 'Settings' },
        { icon: 'help', text: 'Help' },
        { icon: 'phonelink', text: 'App downloads' }
      ]
  })
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
