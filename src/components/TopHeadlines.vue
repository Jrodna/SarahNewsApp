<!-- This is where you should call the api then pass the results, page number and total to the list -->
<!-- Watch for changes on the search and filter -->

<script setup>
import ArticleList from "./ArticleList.vue";
</script>
<script>
export default {
  data() {
    return {
      search: "",
      activeSearch: "",
      country: "NZ",
      items: [
        { title: "Argentina", value: "AR" },
        { title: "Australia", value: "AU" },
        { title: "Austria", value: "AT" },
        { title: "Belgium", value: "BE" },
        { title: "Brazil", value: "BR" },
        { title: "Bulgaria", value: "BG" },
        { title: "Canada", value: "CA" },
        { title: "China", value: "CN" },
        { title: "Colombia", value: "CO" },
        { title: "Cuba", value: "CU" },
        { title: "Czech Republic", value: "CZ" },
        { title: "Egypt", value: "EG" },
        { title: "France", value: "FR" },
        { title: "Germany", value: "DE" },
        { title: "Greece", value: "GR" },
        { title: "Hong Kong", value: "HK" },
        { title: "Hungary", value: "HU" },
        { title: "India", value: "IN" },
        { title: "Indonesia", value: "ID" },
        { title: "Ireland", value: "IE" },
        { title: "Israel", value: "IL" },
        { title: "Italy", value: "IT" },
        { title: "Japan", value: "JP" },
        { title: "Korea, Republic of", value: "KR" },
        { title: "Latvia", value: "LV" },
        { title: "Lithuania", value: "LT" },
        { title: "Malaysia", value: "MY" },
        { title: "Mexico", value: "MX" },
        { title: "Morocco", value: "MA" },
        { title: "Netherlands", value: "NL" },
        { title: "New Zealand", value: "NZ" },
        { title: "Nigeria", value: "NG" },
        { title: "Norway", value: "NO" },
        { title: "Philippines", value: "PH" },
        { title: "Poland", value: "PL" },
        { title: "Portugal", value: "PT" },
        { title: "Romania", value: "RO" },
        { title: "Russian Federation", value: "RU" },
        { title: "Saudi Arabia", value: "SA" },
        { title: "Singapore", value: "SG" },
        { title: "Slovakia", value: "SK" },
        { title: "Slovenia", value: "SI" },
        { title: "South Africa", value: "ZA" },
        { title: "Sweden", value: "SE" },
        { title: "Switzerland", value: "CH" },
        { title: "Taiwan", value: "TW" },
        { title: "Thailand", value: "TH" },
        { title: "Turkey", value: "TR" },
        { title: "Ukraine", value: "UA" },
        { title: "United Arab Emirates", value: "AE" },
        { title: "United Kingdom", value: "GB" },
        { title: "United States", value: "US" },
        { title: "Venezuela", value: "VE" },
      ],
    };
  },
  methods: {
    searchClick() {
      this.activeSearch = this.search;
    },
  },
};
</script>
<template>
  <v-container>
    <v-row>
      <v-col
        ><v-select
          v-model="country"
          :items="items"
          label="Country"
          density="comfortable"
        >
        </v-select
      ></v-col>
      <v-col
        ><v-text-field
          v-model="search"
          placeholder="Search"
          append-inner-icon="mdi-magnify"
          @click:append-inner="searchClick"
          @click:clear="searchClick"
          clearable
          v-on:keyup.enter="searchClick"
          density="comfortable"
        />
      </v-col>
    </v-row>
  </v-container>

  <ArticleList
    v-bind:country="country"
    v-bind:search="activeSearch"
  ></ArticleList>
</template>

<style></style>
