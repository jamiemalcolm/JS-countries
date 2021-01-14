<template>
  <option v-bind="country" v-on:click="countryInfo">{{ country.name }}</option>
  <!--  -->
  <!-- <li v-on:click="countryInfo">{{ country.name }}</li> -->
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
  components: {},
};
</script>

<style scoped>
li {
  list-style: none;
}
</style>