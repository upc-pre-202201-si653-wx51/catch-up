<template>
  <div v-for="article in articles" :key="article.title">
    <v-card class="my-3" hover>
      <v-img height="350px" v-bind:src="article.urlToImage"></v-img>
      <v-container fill-height fluid>
        <v-layout>
          <v-flex xs12 align-end d-flex>
            <span class="headline">{{ article.title }}</span>
          </v-flex>
        </v-layout>
      </v-container>
      <v-card-text>
        {{ article.description }}
      </v-card-text>
      <v-card-actions>
        <v-chip class="ma-2" size="small" color="secondary" text-color="white">
          {{ article.source.name }}
        </v-chip>
        <v-spacer></v-spacer>
        <v-btn icon="mdi-reddit" color="red">
        </v-btn>
        <v-btn icon class="light-blue--text">
          <v-icon small>mdi-twitter</v-icon>
        </v-btn>
        <v-btn icon class="blue--text text--darken-4">
          <v-icon small>mdi-facebook</v-icon>
        </v-btn>
        <v-btn icon class="red--text">
          <v-icon small>mdi-google-plus</v-icon>
        </v-btn>
        <v-btn icon class="blue--text text--darken-4">
          <v-icon small>mdi-linkedin</v-icon>
        </v-btn>
        <v-spacer></v-spacer>
        <v-btn small replace color="info" v-bind:href="article.url" target="_blank">Read More</v-btn>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
export default {
  name: "MainContent",
  props: {
    articles: Array
  }
}
</script>

<style scoped>

</style>
