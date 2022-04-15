<template>
  <v-app light>
    <v-app-bar app color="primary">
      <v-app-bar-title class="white--text">CatchUp</v-app-bar-title>
    </v-app-bar>
    <v-main>
      <main-content :articles="articles"></main-content>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import MainContent from "./components/main-content.vue";
import axios from "axios";

export default {
  name: 'App',

  components: {
    HelloWorld,
    MainContent
  },

  data() {
    return {
      //
      apiKey: 'fecf4feeffa64e4da682e7d268612ce5',
      articles: [],
      errors: [],
    };
  },

  created() {
    this.getArticlesForSource('bbc-news');
  },

  methods: {
    getArticlesForSource(sourceId) {
      axios.get(`https://newsapi.org/v2/top-headlines?sources=${sourceId}&apiKey=${this.apiKey}`)
          .then(response => {
            this.articles = response.data.articles;
            console.log(response.data);
          })
          .catch(error => {
            this.errors.push(error);
            console.log(error);
          });
    }
  }
}
</script>
