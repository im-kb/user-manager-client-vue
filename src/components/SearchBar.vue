<template>
  <div class="input-group">


    <input type="text" id="example-input1-group2" name="example-input1-group2" class="form-control"
           placeholder="Search for user" v-model="search">
    <span class="input-group-btn">
                            <button type="button" class="btn btn-effect-ripple btn-primary"><i class="fa fa-search"></i></button>
        </span>
  </div>
</template>

<script>
export default {
  name: "SearchBar",
  props: {
    users: Array,
    user: Object,
  }, data() {
    return {
      search: "",
    }
  },
  computed: {
    filteredList() {
      console.log("bll");
      return this.users.filter(user => {
        return user.name.toLowerCase().includes(this.search.toLowerCase());
      })
    }
  }
}
</script>

<style scoped>

</style>
