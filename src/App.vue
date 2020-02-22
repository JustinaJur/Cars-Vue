<template>
  <div id="app">
    <Header msg="Cars" />
    <Card :cars="cars" :addCar="addCar" />
  </div>
</template>

<script>
import Card from "./components/Card.vue";
import Header from "./components/Header.vue";
import { getCars } from "./api/api.js";

export default {
  name: "App",
  components: {
    Card,
    Header
  },
  data() {
    return {
      cars: []
    };
  },
  mounted() {
    this.addCar();
  },

  methods: {
    async addCar() {
      const car = await getCars();
      this.cars = [...this.cars, car];
    }
  }
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
