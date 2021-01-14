<template>
  <div>
    <list-item
      v-for="(country, index) in countries"
      :country="country"
      :key="index"
    ></list-item>
  </div>
</template>

<script>
import Country from "./Country.vue";
import CountriesDropDown from "./CountriesDropDown.vue";

export default {
  name: "countries-list",
  props: ["countries"],
  components: {
    "list-item": Country,
    "countries-drop-down": CountriesDropDown,
  },
};
</script>

<style>
</style>