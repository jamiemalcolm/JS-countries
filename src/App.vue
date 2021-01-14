<template>
  <div class="main-container">
    <!-- <countries-drop-down :countries="countries"></countries-drop-down> -->
    <countries-list :countries="countries"></countries-list>
    <country-info :country="selectedCountry"></country-info>
  </div>
</template>

<script>
import { eventBus } from "./main.js";
import CountriesList from "./components/CountriesList.vue";
import CountryInfo from "./components/CountryInfo.vue";
import CountriesDropDown from "./components/CountriesDropDown.vue";

export default {
  name: "App",
  data() {
    return {
      countries: [],
      selectedCountry: null,
    };
  },
  components: {
    "countries-list": CountriesList,
    "country-info": CountryInfo,
    "countries-drop-down": CountriesDropDown,
  },
  mounted() {
    fetch("https://restcountries.eu/rest/v2/all")
      .then((res) => res.json())
      .then((countries) => (this.countries = countries));

    eventBus.$on("country-selected", (country) => {
      this.selectedCountry = country;
    });
  },
};
</script>

<style scoped>
.main-container {
  display: flex;
  justify-content: space-between;
}
</style>
