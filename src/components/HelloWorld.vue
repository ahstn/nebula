<template>
  <v-container>
    <v-layout>
      <v-flex xs3 ma-2>
        <v-expansion-panel class="py-3 elevation-0">
          <draggable :list="apps" group="apps" class="mx-4">
            <v-expansion-panel-content
              v-for="(item, index) in apps" :key="index" class="elevation-1">
            <template v-slot:header>
                <div>{{ item.name }}</div>
              </template>
              <v-card class="overrides">
                <v-card-text class="px-4 py-0">
                  <span class="font-weight-medium">Overrides:</span>
                  <v-checkbox
                    v-model="item.overrides.image" label="Image" class="ma-0" />
                </v-card-text>
              </v-card>
            </v-expansion-panel-content>
          </draggable>
        </v-expansion-panel>
      </v-flex>

      <v-flex xs3 ma-2>
        <v-expansion-panel class="py-3 elevation-0">
          <draggable :list="bundle" group="apps">
            <v-expansion-panel-content
              v-for="(item, index) in bundle" :key="index" class="elevation-1">
            <template v-slot:header>
                <div>{{ item.name }}</div>
              </template>
              <v-card class="overrides">
                <v-card-text class="px-4 py-0">
                  <span class="font-weight-medium">Overrides:</span>
                  <v-checkbox
                    v-model="item.overrides.image" label="Image" class="ma-0" />
                </v-card-text>
              </v-card>
            </v-expansion-panel-content>
          </draggable>
        </v-expansion-panel>
      </v-flex>

      <v-flex xs3 ma-2>
        <Displayer class="ma-2" :value="bundle" title="YAML" />
      </v-flex>
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
        { name: "auth", id: 0, overrides: { image: true } },
        { name: "billing", id: 1, overrides: { image: false } },
        { name: "payments", id: 2, overrides: { image: false } },
        { name: "processor", id: 3, overrides: { image: false } },
        { name: "membership", id: 4, overrides: { image: false } },
        { name: "subscriber", id: 5, overrides: { image: false } }
      ],
      bundle: [
        { name: "auth", id: 0, overrides: { image: true } }
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

<style lang="stylus">
  .v-expansion-panel>div
    width: 100%

  .overrides
    .v-label
      font-size: 14px
    .v-input__slot
      margin-bottom: none!important
</style>
