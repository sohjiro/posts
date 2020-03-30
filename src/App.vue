<template>
  <div id="app">
    <Post v-for="post in posts" :key="post.id" :post="post" />
  </div>
</template>

<script>
import Post from './components/Post.vue'
import axios from "axios"

export default {
  name: 'App',
  components: {
    Post
  },
  data: () => {
    return {
      posts: []
    }
  },
  mounted: function() {
    axios.get("https://jsonplaceholder.typicode.com/posts")
      .then((result) => {
        this.posts = result.data
      })
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
