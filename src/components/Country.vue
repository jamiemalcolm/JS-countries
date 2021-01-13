<template>
  <div>
    <li>{{country.name}}</li>
  </div>
</template>

<script>
export default {
  name: "list-item",
  props: ["country"],
};
</script>

<style>
</style>