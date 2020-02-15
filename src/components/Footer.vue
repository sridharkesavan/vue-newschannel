<template>
  <div>
    <footer class="social">
      <ul>
        <li><facebook :url="url" scale="2"></facebook></li>
        <li><twitter :url="url" title="Check me on Github" scale="2"></twitter></li>
        <li><linkedin :url="url" scale="2"></linkedin></li>
      </ul>
    </footer>
  </div>
</template>

<script>
import { Facebook, Twitter, Linkedin } from "vue-socialmedia-share";

export default {
  name: "App",
  components: {
    Facebook,
    Twitter,
    Linkedin
  }
};
</script>

<style scoped>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333333;
}

li {
  float:left;
  margin-left: 20px;
  margin-inline: 10px;
  justify-items:flex-end;
}

li a:hover {
  background-color: #111111;
}
</style>