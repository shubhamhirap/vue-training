<template>
  <!-- conditional List Rendering -->
  <template v-for="name in names" :key="name">
    <h2 v-if="name === 'lucifer'">{{ name }}</h2>
  </template>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      names: ["devil", "lucifer", "man of mayhem"],
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
