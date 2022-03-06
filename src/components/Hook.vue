<template>
  <div>
    <h1>{{ name }}</h1>
    <button @click="ChangeName()">Click Me !</button>
  </div>
</template>

<script>
export default {
  name: "Hook",
  data() {
    return {
      name: " Hook Part",
    };
  },
  methods: {
    ChangeName() {
      this.name = "Hook Hook Hook";
    },
  },
  beforeCreate() {
    alert("Before Created Hook");
  },
  created() {
    alert("Hook Created");
  },
  beforeUpdate() {
    alert("Before Update");
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
</style>
