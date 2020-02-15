<template>
  <div class="top-news-container">
    <ul>
      <li class="news-group" v-for="(value, index) in CurrentTopnews" v-bind:key="index">
        <b-media tag="li">
          <template v-slot:aside>
            <b-img
              :src="CurrentTopnews[index].urlToImage"
              height="100"
              width="150"
              alt="placeholder"
            ></b-img>
          </template>
          <h5 class="mt-0mb-1" @click="myFunction(CurrentTopnews[index].url)">
            Article
            <a>{{CurrentTopnews[index].title}}</a>
          </h5>
          <p class="mb-0">{{CurrentTopnews[index].description}}</p>
          <p class="mb-1">{{CurrentTopnews[index].author}}</p>
        </b-media>
      </li>
    </ul>
  </div>
</template> 

<script>
export default {
  props: {
    CurrentTopnews: Object
  },
  data() {
    return {
      index: 0
    };
  },
  methods: {
    myFunction: function(url) {
      window.open(url, "_blank");
    }
  }
};
</script>

<style scoped>
.news-group {
  list-style-type: none;
  margin-top: 20px;
  margin-bottom: 10px;
  text-align: center;
}
.mt-0mb-1 .h5 {
  text-align: center;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 150%;
  color: yellow;
}
.mb-0 {
  font-family: Arial, Helvetica, sans-serif;
  text-align: justify;
}
.mb-1 {
  text-align: left;
  font-family: Arial, Helvetica, sans-serif;
  text-align-last: right;
  margin: 0%;
}
.media:hover {
  background: #eee;
  cursor: pointer;
}
</style>