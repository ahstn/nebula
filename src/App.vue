<template>
  <v-app>
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

    <v-layout row pb-2>
      <v-flex xs8 offset-xs2>
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
  data () {
    return {
      //
    }
  }
}
</script>

<style>
  .card--flex-toolbar {
    margin-top: -64px;
  }
</style>
