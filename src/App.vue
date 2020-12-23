<template>
  <div>
    <!-- array of strings -->
    <h2 v-for="(name, index) in names" :key="name">
      {{ index + 1 }}. {{ name }}
    </h2>

    <!-- Array of objects -->
    <h2 v-for="name in fullNames" :key="name.firstName">
      {{ name.firstName }} {{ name.lastName }}
    </h2>

    <!-- Array of arrays -->
    <div v-for="actor in actors" :key="actor.name">
      <h2>{{ actor.name }}</h2>
      <h3 v-for="movie in actor.movies" :key="movie">{{ movie }}</h3>
    </div>

    <!-- Iterate over the object properties -->
    <!-- order of value, key and index matter in v-for -->
    <h2 v-for="(value, key, index) in myInfo" :key="value">
      {{ index + 1 }}. {{ key }} : {{ value }}
    </h2>

    <!-- v-for also support with template tag -->
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      names: ["devil", "lucifer", "man of mayhem"],
      fullNames: [
        {
          firstName: "John",
          lastName: "Cena",
        },
        {
          firstName: "Sheldon",
          lastName: "Cooper",
        },
        {
          firstName: "Adolf",
          lastName: "Hitler",
        },
      ],
      actors: [
        {
          name: "Emraan Hashmi",
          movies: ["murder 2", "Jannat", "Awarapan"],
        },
        {
          name: "Vijay Deverakonda",
          movies: ["Arjun Reddy", "Dear Comrade"],
        },
      ],
      myInfo: {
        name: "Lucifer",
        address: "Las Vegas",
      },
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
