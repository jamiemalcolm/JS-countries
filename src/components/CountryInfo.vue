<template>
  <div v-if="country">
    <p>{{ country.capital }}</p>
    <p>{{ country.population }}</p>
  </div>
</template>

<script>
export default {
  name: "country-info",
  props: ["country"],
};
</script>

<style>
</style>