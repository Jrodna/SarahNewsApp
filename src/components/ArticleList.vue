<template>
  <div v-if="errored">
    <h1>
      An error has occured <br />
      Please try again later
    </h1>
  </div>
  <div v-if="loading">Loading...</div>

  <v-container>
    <v-row>
      <v-col v-for="article in articles" :key="article.id" cols="4">
        <v-card height="300">
          <v-img max-height="50%" cover v-bind:src="article.urlToImage" />
          <v-card-text>{{ article.title }}</v-card-text>
          <v-card-subtitle>{{ article.author }}</v-card-subtitle>
          <v-card-actions
            ><v-btn icon="mdi-earth" :href="article.url"></v-btn
          ></v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
  <v-pagination
    v-model="page"
    totalVisible="5"
    :length="Math.ceil(this.totalResults / this.pageSize)"
  ></v-pagination>
</template>

<script>
export default {
  props: ["search", "country"],
  data() {
    return {
      articles: [],
      loading: true,
      errored: false,
      page: 1,
      pageSize: 9,
      totalResults: 0,
    };
  },
  mounted() {
    this.getArticles();
  },
  methods: {
    getArticles() {
      // this.articles = [
      //   { title: "article1" },
      //   { title: "article2", author: "author" },
      // ];
      // return;
      const api = "https://newsapi.org/v2/top-headlines";
      const params = {
        apiKey: "d36d9da7ad2746268e11edc18bc5e445",
        page: this.page,
        pageSize: this.pageSize,
      };
      if (this.search) {
        params.q = this.search;
      }
      if (this.country) {
        params.country = this.country.toLowerCase();
      }
      this.axios
        .get(api, { params })
        .then((response) => {
          this.articles = response.data.articles;
          this.totalResults = response.data.totalResults;
        })
        .catch((error) => {
          console.log(error);
          this.errored = true;
        })
        .finally(() => {
          this.loading = false;
        });
    },
  },
  watch: {
    search() {
      this.page = 1;
      this.getArticles();
    },
    country() {
      this.page = 1;
      this.getArticles();
    },
    page() {
      this.getArticles();
    },
  },
};
</script>

<style scoped>
p,
h3,
ul {
  margin: 0;
  padding: 10px;
  list-style-type: none;
}

img {
  width: 150px;
  position: cover;
}

.listContainer {
  background-color: rgb(3, 30, 70, 0.7);
}

.listContainer li {
  list-style-type: none;
  background-color: rgb(251, 233, 197);
  color: rgb(3, 30, 70);
  margin: 20px auto;
  padding: 10px 20px;
  border-radius: 10px;
  display: flex;
  align-items: center;
}
</style>
