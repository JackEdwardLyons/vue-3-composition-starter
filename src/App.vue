<template>
  <section id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />

    <br />
    
    <div>
      <h3>Vue 3 Composition example</h3>
      <p>Capacity: {{ capacity }}</p>
      <button @click="increaseCapacity()">Increase Capacity</button>
    </div>
  </section>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import { ref } from "@vue/composition-api";

export default {
  name: "app",
  components: {
    HelloWorld
  },
  setup() {
    const capacity = ref(3);

    function increaseCapacity() {
      capacity.value++;
    }
    return { capacity, increaseCapacity };
  },
  mounted () {
    /* eslint-disable */
    console.log({ app: process.env.VUE_APP_STOCK_DATA_API_KEY })
  }
};
</script>


<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
