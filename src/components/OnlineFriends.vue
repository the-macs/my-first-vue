<template>
  <div id="onlinefriend">
    <h2>Online Friends</h2>
    <div v-for="(friend, index) in friends" :key="index">
      <h5 v-if="friend.online">{{ friend.name }}</h5>
    </div>
  </div>
</template>

<script>
export default {
  name: "OnlineFriends",
  props: ["friends"],
  data() {
    return {};
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
