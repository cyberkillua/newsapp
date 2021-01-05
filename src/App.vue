<template>
  <div id="app">
    <div>
      <h1>News!!!!</h1>
      <h1>Newss show here</h1>
      <!-- <div v-bind:key="article.id" v-for="article in news">
        <Displaynews :article="article" />
      </div> -->
    </div>
  </div>
</template>

<script>
import axios from "axios";
// import Displaynews from "./components/Displaynews";
export default {
  name: "App",
  data() {
    return {
      news: [],
    };
  },
  components: {
    // Displaynews,
  },
  created() {
    axios
      .get(
        "https://cryptocontrol.io/api/public/", {
          headers:{
            "Authorization": "Bearer 94981ef81899cb1975ec0daaeed63250"
          }
        }
      )
      .then((res) => {
        this.news = res.data;
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
</style>
