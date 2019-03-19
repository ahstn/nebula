<template>
  <v-container>
    <v-layout
      text-xs-center
      wrap
    >
      <v-expansion-panel class="ma-2 py-2">
        <draggable :list="apps" group="apps" class="mx-4">
          <v-expansion-panel-content v-for="(item, index) in apps" :key="index" class="elevation-1">
           <template v-slot:header>
              <div>{{ item.name }}</div>
            </template>
            <v-card>
              <v-card-text>Lorem ipsum dolor sit amet</v-card-text>
            </v-card>
          </v-expansion-panel-content>
        </draggable>

        <draggable :list="bundle" group="apps" class="mx-4">
          <v-expansion-panel-content v-for="(item, index) in bundle" :key="index" class="elevation-1">
           <template v-slot:header>
              <div>{{ item.name }}</div>
            </template>
            <v-card>
              <v-card-text>Lorem ipsum dolor sit amet</v-card-text>
            </v-card>
          </v-expansion-panel-content>
        </draggable>
      </v-expansion-panel>

      <Displayer class="col-3" :value="bundle" title="YAML" />
    </v-layout>
  </v-container>
</template>

<script>
import Displayer from './Displayer'
import draggable from "vuedraggable";
let id = 1;

  export default {
    components: {
      draggable,
      Displayer
    },
    data: () => ({
      enabled: true,
      apps: [
        { name: "auth", id: 0 },
        { name: "billing", id: 1 },
        { name: "payments", id: 2 },
        { name: "processor", id: 3 },
        { name: "membership", id: 4 },
        { name: "subscriber", id: 5 }
      ],
      bundle: [
        { name: "auth", id: 0 }
      ],
      dragging: false
    }),
    computed: {
      draggingInfo() {
        return this.dragging ? "under drag" : "";
      }
    }
  }
</script>

<style>

</style>
