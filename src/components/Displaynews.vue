<template>
  <div class="onecard">
      <div class="imgcard">
    <img v-bind:src="article.image" />
      </div>
    <div class="textcard">
    <h2>{{ article.title }}</h2>
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
   margin-bottom: 50px;
  font-family: 'Fira Sans', sans-serif;
}
a {
  color: #ff9933;
  text-decoration: none;
  font-style: italic;
  padding-top: 10px;
}
img {
  height: 250px;
  width: 300px;
  margin: 10px;
}
.textcard {
    padding: 0 10px 0 10px;
    height: 250px;
    width: 40%;
    margin: 0 10px 10px 50px;
}
@media screen and (max-width: 768px) {
  .onecard {
    display: block;
    margin-bottom: 50px;
  }
  .textcard {
    padding: 0;
    height: fit-content;
    width: 80%;
    margin: auto;
    /* background-color: green; */
    
}
.imgcard {
    width: 80%;
    margin: auto;
    /* background-color: tomato; */
}
  img {
    height: 150px;
    width: 100%;
    padding: 0;
    margin: 10px 0 10px 0;

  }
}
</style>
