<template>
  <div>
    <h3>{{ title }}</h3>
    <pre class="grey pa-3 ma-1 lighten-3">
  apiVersion: apps/v1
  kind: Kustomization

  {{ buildYAML }}
    </pre>
  </div>
</template>
<script>
const props = {
  name: "Displayer",
  title: {
    required: true,
    type: String
  },
  value: {
    required: true
  }
};
export default {
  props,
  computed: {
    buildYAML() {
      let yaml = "resources:"

      this.value.forEach((element) => {
        yaml = yaml.concat('\n  - ', element.name)
      });

      yaml = yaml.concat('\n\nimages:')
      this.value.forEach((element) => {
        if (element.overrides.image) {
          yaml = yaml.concat('\n  - name: ahstn/', element.name)
          yaml = yaml.concat('\n    newName: ahstn/', element.name)
          yaml = yaml.concat('\n    newTag: 3.6')
        }
      });

      return yaml
    }
  }
};
</script>
<style scoped>
pre {
  text-align: start;
}
</style>
