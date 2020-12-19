<template>
  <div>
    <!-- text-binding with Mustache syntax -->
    <div>{{ greet }} {{ name }}</div>
    <!-- html binding -->
    <div v-html="singer"></div>

    <!-- attr binding -->
    <h2 v-bind:id="headingId">Heading</h2>
    <button v-bind:disabled="isDisabled">Bind</button>
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
      headingId: "heading",
      isDisabled: true,
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
