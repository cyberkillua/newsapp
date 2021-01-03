<template>
  <div id="app">
    <h1>News!!!!</h1>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "App",
  data() {
    return {
      news: [],
    };
  },
  components: {},
  created() {
    axios.get('http://newsapi.org/v2/top-headlines?country=ng&category=entertainment&apiKey=2e8cb925a0bc45a794469a2bb233b93e')
    .then((res=> {
      this.news = res.data.articles
    }))
  },
};
</script>

<style>
#app {
  margin: 0;
}
</style>
