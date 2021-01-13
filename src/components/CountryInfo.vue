<template>
<div>
    <li>{{ country.capital }}</li>
    <li>{{ country.population }}</li>
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