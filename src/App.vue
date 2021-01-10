<template>
  <div>
    <h2>FullName - {{ firstName }} {{ lastName }}</h2>
    <!-- with computed property -->
    <h2>Fullname (with computed property) - {{ fullName }}</h2>
    <button @click="items.push({ id: 7, title: 'audi', price: 21000 })">
      Add Item
    </button>
    <h3>Computed Total - ${{ total }}</h3>
    <h3>Method Total - ${{ getTotal() }}</h3>
    <input type="text" v-model="country" />
    <div v-for="item in items" :key="item.id">
      <h2 v-if="item.price > 15000">{{ item.title }} {{ item.price }}</h2>
    </div>
    <h2 v-for="item in expensiveItems" :key="item.id">
      Computed -> {{ item.title }} {{ item.price }}
    </h2>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      firstName: "Ross",
      lastName: "Galler",
      items: [
        { id: 1, title: "Honda", price: 12000 },
        { id: 2, title: "ford", price: 10000 },
        { id: 3, title: "BMW", price: 22000 },
        { id: 4, title: "Hundai", price: 9000 },
        { id: 5, title: "Dodge", price: 18000 },
        { id: 6, title: "volkwagon", price: 14000 },
      ],
      country: "",
    };
  },
  methods: {
    getTotal() {
      console.log("total method");
      return this.items.reduce(
        (total, current) => (total = total + current.price),
        0
      );
    },
  },
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`;
    },
    total() {
      console.log("computed");
      return this.items.reduce(
        (total, current) => (total = total + current.price),
        0
      );
    },
    expensiveItems() {
      return this.items.filter((item) => item.price > 15000);
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
