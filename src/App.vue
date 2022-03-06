<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <Navbar />
    <Hook />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Hook from "./components/Hook.vue";

export default {
  name: "App",
  components: {
    Navbar,
    Hook,
  },
  data() {
    return {
      title: "Wow , it works !",
    };
  },
  methods: {},
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
