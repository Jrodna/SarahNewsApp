<!-- This is where you should call the api then pass the results, page number and total to the list -->
<!-- Watch for changes on the search and filter -->

<script setup>
import ArticleList from "./ArticleList.vue";
import SearchArticles from "./SearchArticles.vue";
import FilterArticles from "./FilterArticles.vue";
</script>
<template>
  <SearchArticles />
  <FilterArticles></FilterArticles>
  <ArticleList></ArticleList>
</template>

<style></style>
