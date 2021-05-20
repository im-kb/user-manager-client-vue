<template>
  <div class="container" id="main-container"  >
    <div class="row" >
      <div  :key="user.id" v-for="user in users" class="col-md-6 col-xl-3 ">
        <div class = col mb-3 >
        <User :user="user"/>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import User from './User'

export default {
  name: 'Users',
  props: {
    users: Array,
  },
  components: {
    User
  }
}


</script>

<style scoped>

</style>
