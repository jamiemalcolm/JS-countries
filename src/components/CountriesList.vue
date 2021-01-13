<template>
  <div>
    <ul>
      <list-item
        v-for="(country, index) in countries"
        :country="country"
        :key="index"
      ></list-item>
    </ul>
  </div>
</template>

<script>
import Country from "./Country.vue";

export default {
  name: "countries-list",
  props: ["countries"],
  components: {
    "list-item": Country,
  },
};
</script>

<style>
</style>