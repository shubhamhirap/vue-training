<template>
  <div>
    <h2>Volume Tracker (0-20)</h2>
    <h3>Current Volume - {{ volume }}</h3>
    <div>
      <button @click="volume += 2">Increase</button>
      <button @click="volume -= 2">Decrease</button>
    </div>
    <input type="text" v-model="movie" />
    <input type="text" v-model="movieInfo.title" />
    <input type="text" v-model="movieInfo.actor" />

    <!-- for array mutation -->
    <div>
      <button @click="movieList.push('Geeta Govindam')">ADD Movie</button>
    </div>

    <!-- For new array ref -->
    <div>
      <button @click="favActors = favActors.concat(['will smith'])">
        ADD Actor
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      volume: 0,
      movie: "Batman",
      movieInfo: {
        title: "",
        actor: "",
      },
      movieList: ["Dear comrade", "Arjun Reddy"],
      favActors: ["Emraan Hashmi", "Vijay Deverakonda"],
    };
  },
  methods: {},
  computed: {},
  watch: {
    volume(newValue, oldValue) {
      newValue > oldValue && newValue === 16
        ? alert(
            "Listening to high volume for a long time may damage your hearing"
          )
        : null;
    },
    movie: {
      handler(newValue) {
        console.log(`Calling API with movie name ${newValue}`);
      },
      immediate: true,
    },
    movieInfo: {
      handler(newValue) {
        console.log(
          `Calling API with movie title = ${newValue.title} and actor = ${newValue.actor}`
        );
      },
      deep: true,
    },
    movieList: {
      handler(newValue) {
        console.log(`Updated List ${newValue}`);
      },
      deep: true,
    },
    favActors: {
      handler(newValue) {
        console.log(`Updated favActors List ${newValue}`);
      },
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
</style>
