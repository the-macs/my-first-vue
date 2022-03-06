<template>
  <div id="allfriend">
    <h2>All Friends</h2>
    <div v-for="(friend, index) in friends" :key="index">
      <h5 @click="unfriend(friend.name)">{{ friend.name }}</h5>
    </div>
  </div>
</template>

<script>
export default {
  name: "AllFriends",
  props: ["friends"],
  data() {
    return {};
  },
  methods: {
    unfriend(name) {
      this.$emit("delete", { name });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
nav {
  text-align: center;
}

nav ul {
  padding: 0;
}

nav li {
  display: inline-block;
  list-style-type: none;
  margin: 0;
  padding: 8px;
}
</style>
