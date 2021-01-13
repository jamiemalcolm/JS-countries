<template>
  <div>
    <li v-on:click="countryInfo">{{ country.name }}</li>
  </div>
</template>

<script>
import { eventBus } from "../main.js";
// import CountryInfo from "./CountryInfo.vue";

export default {
  name: "list-item",
  props: ["country"],
  methods: {
    countryInfo: function () {
      eventBus.$emit("country-selected", this.country);
    },
  },
};
</script>

<style scoped>
li {
  list-style: none;
}
</style>