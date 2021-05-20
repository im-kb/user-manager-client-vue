<template>
  <Header title="Client manager" :users="users">


  </Header>
  <div>
    <b-table :users="users" :fields="users" caption-top>
      <template #table-caption>This is a table caption at the top.</template>
    </b-table>
  </div>

  <Users :users="users"></Users>
  <EditModal></EditModal>


  <link href="http://maxcdn.bootstrapcdn.com/font-awesome/4.1.0/css/font-awesome.min.css" rel="stylesheet">
  <!--  npm run serve &#45;&#45; &#45;&#45;port 3000-->
</template>

<script>

import Header from './components/Header'
import Users from "@/components/Users";
import EditModal from "@/components/EditModal";
import "bootstrap/dist/css/bootstrap.min.css";

export default {
  name: 'App',
  components: {
    EditModal,
    Users,
    Header,
  },
  data() {
    return {
      users: []
    }
  },
  methods: {

    async fetchUsers() {
      const response = await fetch('http://localhost:8080/users/all');
      const data = await response.json();

      return data;
    },


  },

  async created() {
    this.users = await this.fetchUsers()
  },
}
</script>

<style>

</style>

