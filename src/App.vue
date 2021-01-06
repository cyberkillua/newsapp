<template>
  <div id="app">
    <div>
      <h1>News!!!!</h1>
      <h1>Newss show here</h1>
      <div v-bind:key="article.id" v-for="article in news">
        <Displaynews :article="article" />
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Displaynews from "./components/Displaynews";
export default {
  name: "App",
  data() {
    return {
      news: [],
    };
  },
  components: {
    Displaynews,
  },
  created() {
    axios
      .get(
        "http://newsapi.org/v2/everything?q=bitcoin&from=2020-12-06&sortBy=publishedAt&apiKey=2e8cb925a0bc45a794469a2bb233b93e"
      )
      .then((res) => {
        this.news = res.data.articles;
      })
      .catch((error) => {
        console.log(error.response);
      });
  },
};
</script>

<style>
body {
  margin: 0;
  background-color: #020202;
  color: #fafafa;
}
#app {
  margin: auto;
  width: 60%;
}
@media screen and (max-width: 768px) {
  #app {
    width: 90%;
    margin: auto;
  }
}
</style>
