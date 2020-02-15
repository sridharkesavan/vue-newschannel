<template>
  <div id="app">
    <Header/>
    <b-container class="bv-example-row">
      <b-row>
        <b-col sm="8" offset="2">
          <Topnews :CurrentTopnews="topnews" />
        </b-col>
      </b-row>
    </b-container>
    <Footer/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Topnews from "./components/Topnews.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Header,
    Topnews,
    Footer
  },
  data() {
    return {
      topnews: [],
      index: 0
    };
  },
  mounted: function() {
    fetch(
      "https://newsapi.org/v2/top-headlines?sources=google-news&apiKey=facff4ddd0e249678b5d383f0f9da90c",
      {
        method: "get"
      }
    )
      .then(response => {
        return response.json();
      })
      .then(jsonData => {
        this.topnews = jsonData.articles;
      });
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
