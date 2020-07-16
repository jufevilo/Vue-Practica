<template>
  <div id="app">
    <img alt="Vue logo" src="../assets/logo.png" />
    <div class="post-box my-5 mx-5" v-for="post in posts" :key="post.id">
      <h3>{{ post.title }}</h3>
      <p>{{ post.body }}</p>
      <a class="btn btn-info mx-5" href="#" role="button">Click</a>
    </div>
  </div>
</template>
<script>
// Declarar la librería
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      posts: [],
    };
  },
  // Evento
  mounted() {
    axios
      .get("https://jsonplaceholder.typicode.com/posts?_limit=5")
      .then((response) => (this.posts = response.data));
  },
};
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  text-align: center;
  margin-top: 60px;
}

.post-box {
  display: flex;
  flex-flow: column;
  justify-content: center;
  height: 200px;
  width: auto;
  box-shadow: 0px 0px 5px #888888;
  border-radius: 5px;
}
</style>
