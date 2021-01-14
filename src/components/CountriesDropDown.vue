<template>
  <div>
    <select v-model="countries" v-on:click="countryInfo">
      <country></country>
    </select>
  </div>
</template>

<script>
import { eventBus } from "../main.js";

export default {
  name: "countries-drop-down",
  props: ["country"],
  methods: {
    countryInfo: function () {
      eventBus.$emit("country-selected", this.country);
    },
  },
};
</script>

<style>
</style>