<template>
  <div id="app">
    <div>
      <div class="navcard">
        <p>Daily Crypto News</p>
      </div>
      <div class="articlecard" v-bind:key="article.id" v-for="article in news">
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
        "https://newsapi.org/v2/everything?language=en&q=bitcoin&from=2020-12-06&sortBy=publishedAt&apiKey=2e8cb925a0bc45a794469a2bb233b93e"
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
.articlecard {
  margin: auto;
  width: 60%;
}
.navcard {
  background-color: #262626;
  width: 100%;
  height: 100px;
  margin-bottom: 70px;
  color: #ff9933;
  font-family: 'Montserrat', sans-serif;
  font-size: xx-large;
  justify-content: center;
  align-items: center;
  display: flex;
}

@media screen and (max-width: 768px) {
  .articlecard {
    width: 100%;
    margin: auto;
  }
}
@media (max-width: 1024px) {
  .articlecard {
    width: 100%;
    margin: auto;
  }
}
</style>
