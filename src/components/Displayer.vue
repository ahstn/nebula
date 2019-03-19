<template>
  <div>
    <h3>{{ title }}</h3>
    <pre class="grey pa-3 ma-1 lighten-3">{{ valueString }}</pre>
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
    valueString() {
      return JSON.stringify(this.value, null, 2);
    }
  }
};
</script>
<style scoped>
pre {
  text-align: start;
}
</style>
