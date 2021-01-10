<template>
  <div>
    <!-- v-once directive - renders corresponding HTML element only once -->
    <h2 v-once>{{ name }}</h2>
    <button @click="name = 'batman'">Submit</button>
    <!-- v-pre - skips comilation for corresponding element i.e. it renders element as it is on screen -->
    <h2 v-pre>{{ name }}</h2>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "vishwas",
    };
  },
  methods: {},
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
