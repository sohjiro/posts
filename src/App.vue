<template>
  <div id="app">
    <Posts v-for="post in posts" :key="post.id" :post="post" />
  </div>
</template>

<script>
import Posts from './components/Posts.vue'
import axios from "axios"

export default {
  name: 'App',
  components: {
    Posts
  },
  data: () => {
    return {
      posts: []
    }
  },
  mounted: function() {
    axios.get("https://jsonplaceholder.typicode.com/posts")
      .then((result) => {
        console.log(result.data)
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
