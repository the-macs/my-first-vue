<template>
  <div>
    <h1>Posts</h1>
    <hr />
    <input type="text" v-model="searchTerm" placeholder="Search ..." />
    <div v-for="post in filtersearch" :key="post.id">
      <h2>{{ post.title }}</h2>
      <p>{{ post.body | snippet }}</p>
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
      searchTerm: "",
    };
  },
  computed: {
    filtersearch() {
      return this.posts.filter((post) => {
        return post.title.match(this.searchTerm);
      });
    },
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
