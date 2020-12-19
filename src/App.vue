<template>
  <div>
    <!-- text-binding with Mustache syntax -->
    <div>{{ greet }} {{ name }}</div>
    <!-- html binding -->
    <div v-html="singer"></div>

    <!-- attr binding -->
    <h2 v-bind:id="headingId">Heading</h2>
    <button v-bind:disabled="isDisabled">Bind</button>

    <!-- Binding to class -->
    <!-- Static class -->
    <h2 class="text-color">Static Class</h2>

    <!-- v-bind class binding -->
    <h3 v-bind:class="status">v-bind Class Binding</h3>

    <!-- we can add both static and dynamic class at same time -->
    <h4 class="text-color" v-bind:class="status">static as well as dynamic</h4>

    <!-- conditionally apply class to html element -->
    <h2 v-bind:class="isPromoted && 'promoted'">Conditional class binding</h2>

    <h2 v-bind:class="isSoldOut ? 'sold-out' : 'new'">SoldOut? movie</h2>

    <!-- class binding with array -->
    <h3 v-bind:class="['new', 'promoted']">Newly promoted movie</h3>

    <!-- class binding with array (conditional) -->
    <h3
      v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']"
    >
      Array Conditional
    </h3>

    <!-- Object conditional -->
    <h3
      v-bind:class="{
        promoted: isPromoted,
        new: !isSoldOut,
        'sold-out': isSoldOut,
      }"
    >
      Object Conditional
    </h3>

    <!-- bind style with object syntax -->
    <span
      v-bind:style="{
        backgroundColor: highlightColor,
        padding: '10px',
      }"
    >
      Inline Style
    </span>

    <!-- bind style with styleObject syntax -->
    <span v-bind:style="highlightStyleObject"> Style with styleObject </span>
    <!-- bind style with styleObject syntax -->
    <span v-bind:style="[baseStyleObject, successStyle]">
      style objects with array
    </span>
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
      status: "danger",
      isPromoted: true,
      isSoldOut: true,
      highlightColor: "orange",
      highlightStyleObject: {
        padding: "5px",
        backgroundColor: "#00bfff",
        margin: "5px",
      },
      baseStyleObject: {
        fontSize: "30px",
        margin: "10px",
        padding: "7px",
      },
      successStyle: {
        color: "#228b22",
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
