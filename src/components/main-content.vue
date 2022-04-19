<template>
  <div v-for="article in articles" :key="article.title">
    <article-card :article="article"/>
  </div>
</template>

<script>
import ArticleCard from "./article-card.vue";
export default {
  name: "MainContent",
  components: {ArticleCard},
  props: {
    articles: Array
  }
}
</script>

<style scoped>

</style>
