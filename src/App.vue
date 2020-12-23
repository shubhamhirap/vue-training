<template>
  <div>
    <h2 v-if="num === 0">The number is Zero</h2>
    <h2 v-else-if="num < 0">The number negative</h2>
    <h2 v-else-if="num > 0">The number positive</h2>
    <h2 v-else>The number is not Zero</h2>

    <template v-if="display">
      <h2>Devil</h2>
      <h2>Devil's Diary</h2>
      <h2>Vue</h2>
    </template>

    <h2 v-show="display">Using v-show</h2>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      num: -1,
      display: true,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.text-color {
  color: #908;
}

.promoted {
  font-style: italic;
}

.new {
  color: green;
}
.sold-out {
  color: red;
}
</style>
