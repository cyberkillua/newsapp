<template>
  <div id="app">
    <div>
      <div class="navcard">
        <p>Daily Crypto News</p>
      </div>
      <div class="articlecard" v-bind:key="article.id" v-for="article in news">
        <Displaynews :article="article" />
      </div>
      <div class="footcard"></div>
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
        encodeURI(
          "https://gnews.io/api/v4/search?q=litecoin OR bitcoin OR ethereum OR cryptocurrency&lang=en&token=b25fded44a2a2dbf90c00b381b74a513"
        )
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
  height: 80px;
  margin-bottom: 70px;
  color: #ff9933;
  font-family: "Montserrat", sans-serif;
  font-size: larger;
  justify-content: center;
  align-items: center;
  display: flex;
}
.footcard {
  background-color: #262626;
  width: 100%;
  height: 100px;
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
