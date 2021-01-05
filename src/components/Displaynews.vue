<template>
  <div>
    <h3>{{ article.title }}</h3>
    <p>
      <a
        v-bind:href="article.url"
        target="_blank"
        rel="noopener noreferrer"
        title="domain"
        >{{ article.source.title }}</a
      >
    </p>
  </div>
</template>

<script>
export default {
  name: "Displaynews",
  props: ["article"],
};
</script>

<style  scoped>
    a{
        color: #ff9933;
    }
</style>
