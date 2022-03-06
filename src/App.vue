<template>
  <div id="app">
    <h1>{{ title }}</h1>
    <Navbar />
    <AllFriends :friends="friends" @delete="deleteFriend" />
    <OnlineFriends :friends="friends" />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import AllFriends from "./components/AllFriends.vue";
import OnlineFriends from "./components/OnlineFriends.vue";

export default {
  name: "App",
  components: {
    Navbar,
    AllFriends,
    OnlineFriends,
  },
  data() {
    return {
      title: "Wow , it works !",
      friends: [
        { name: "Esa", online: false },
        { name: "Yossi", online: false },
        { name: "Safaat", online: true },
        { name: "Arman", online: true },
        { name: "Riza", online: false },
      ],
    };
  },
  methods: {
    deleteFriend(payload) {
      // console.log(payload);
      this.friends = this.friends.filter((friend) => {
        return friend.name !== payload.name;
      });
    },
  },
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
