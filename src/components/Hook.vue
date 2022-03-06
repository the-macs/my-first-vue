<template>
  <div>
    <h1>Posts</h1>
    <div v-for="post in posts" :key="post.id">
      <h2>{{ post.title }}</h2>
      <p>{{ post.body }}</p>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Hook",
  data() {
    return {
      posts: [],
    };
  },
  methods: {},
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/posts")
      .then((res) => {
        this.posts = res.data;
      })
      .catch((err) => {
        console.log(err);
      });
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: orangered;
  text-align: center;
}
</style>
