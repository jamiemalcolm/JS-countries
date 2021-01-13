<template>
  <div>
    <li v-on:click="countryInfo">{{ country.name }}</li>
    <div v-if="countryInfoClicked">
      <li>Capital: {{ country.capital }}</li>
      <li>Population: {{ country.population }}</li>
    </div>
    <!-- <country-info></country-info> -->
  </div>
</template>

<script>
import CountryInfo from "./CountryInfo.vue";

export default {
  name: "list-item",
  props: ["country"],
  methods: {
    countryInfo: function () {
      this.countryInfoClicked = true;
    },
  },
  data() {
    return {
      countryInfoClicked: false,
    };
  },
  components: {
    "country-info": CountryInfo,
  },
};
</script>

<style scoped>
li {
  list-style: none;
}
</style>