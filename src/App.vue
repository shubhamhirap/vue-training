<template>
  <div>
    <h2>Methods</h2>
    <!-- Important Point Don't use Arrow function for methods -->
    <h1>Add Method - {{ add(2, 3, 4) }}</h1>
    <h1>multiply method - {{ multiply(baseValue) }}</h1>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      baseMultiplier: 5,
      baseValue: 4,
    };
  },
  methods: {
    add(a, b, c) {
      return a + b + c;
    },
    multiply(num) {
      return num * this.baseMultiplier;
    },
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
