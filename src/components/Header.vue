<template>
  <div class="navbar navbar-expand-md navbar-light bg-light" role="navigation">
    <a class="navbar-brand" href="#">User menager</a>
    <search-bar :users="users"></search-bar>
  </div>
</template>


<script>

import SearchBar from "@/components/SearchBar";
export default {
  name: 'Header',
  components: {SearchBar},
  props: {
    title: String,
    users:Array,
  }
}
</script>

<style scoped>
header {
  display: flex;
}

</style>
