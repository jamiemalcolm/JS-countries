<template>
  <div id="app">
    <countries-list :countries="countries"></countries-list>
  </div>
</template>

<script>
import CountriesList from "./components/CountriesList.vue";

export default {
  name: "App",
  data() {
    return {
      countries: [],
    };
  },
  components: {
    "countries-list": CountriesList,
  },
  mounted() {
    fetch("https://restcountries.eu/rest/v2/all")
      .then((res) => res.json())
      .then((countries) => (this.countries = countries));
  },
};
</script>

<style>
</style>
