<template>
  <div class="onecard">
      <div class="imgcard">
    <img v-bind:src="article.urlToImage" />
      </div>
    <div class="textcard">
    <h3>{{ article.title }}</h3>
    <p>{{ article.description}}</p>
    <p>
      <a
        v-bind:href="article.url"
        target="_blank"
        rel="noopener noreferrer"
        title="domain"
        >{{ article.source.name }}</a
      >
    </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Displaynews",
  props: ["article"],
};
</script>

<style  scoped>
.onecard {
  display: flex;
}
a {
  color: #ff9933;
}
img {
  height: 250px;
  width: 300px;
  margin: 10px;
}
.textcard {
    padding: 10px 10px 0 10px;
    height: 250px;
    width: 50%;
    margin: 10px;
}
@media screen and (max-width: 768px) {
  .onecard {
    display: block;
    /* background-color: tomato; */
  }
  .textcard {
    padding: 0;
    height: fit-content;
    width: 80%;
    margin: auto;
    
}
.imgcard {
    width: 80%;
    margin: auto;
}
  img {
    height: 150px;
    width: 200px;
    padding: 0;
    margin: 10px;
  }
}
</style>
