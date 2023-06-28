<template>
  <chart1 :width="'900px'" :height="'600px'"></chart1>
</template>

<script>
import chart1 from "./components/blog/chart1.vue";

export default {
  name: "App",
  components: {
    chart1
  },
}
</script>

<style>
#app {
}
</style>

