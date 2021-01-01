<template>
  <div>
    <h2>Binary - {{ binary }}</h2>
    <!-- v-on directive followed by event -->
    <div>
      <button v-on:click="change">Change</button>
    </div>

    <h2>Count - {{ count }}</h2>
    <div>
      <!-- 'v-on:' === '@' for events -->
      <button @click="increment(1)">Increment</button>
      <button @click="decrement(1)">Decrement</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      binary: 0,
      count: 0,
    };
  },
  methods: {
    change() {
      this.binary = 1;
    },
    increment(num) {
      this.count += num;
    },
    decrement(num) {
      this.count -= num;
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
