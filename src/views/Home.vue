<template>
  <div class="page-wrapper">
    <div class="banner">
      <img src="../assets/banner.jpeg" alt="" />
    </div>
    <div class="articles">
      <ul>
        <li v-for="article in articles" :key="article.id">
          <a @click="$router.push({ name: 'details', params: { id: article.id, article: articles[index] } })">
            <div class="image">
              <img class="w-full mt-2 rounded" :src="article.image" height="140" width="210" />
            </div>
            <h3>{{ article.title }}</h3>
            <p>{{ article.content }}</p>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Home",
  data() {
    return {
      articles: [],
    };
  },
  async mounted() {
    const response = await axios.get("http://localhost:3000/articles");
    this.articles = response.data;
  },
};
</script>

<style lang="sass" scoped></style>
