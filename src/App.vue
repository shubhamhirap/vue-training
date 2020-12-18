<template>
  <div>
    <!-- text-binding with Mustache syntax -->
    <div>{{ greet }} {{ name }}</div>
    <!-- text binding with directive syntax -->
    <div v-html="singer"></div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      greet: "Hello",
      name: "Lucifer",
      singer: "<strong>post malone</strong>",
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
</style>
