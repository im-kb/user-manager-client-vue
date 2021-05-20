<template>
  <div class="card">
    <div class="card-body text-center">
      <img v-bind:src="user.imageUrl" style="width:100px;margin-top:-65px"
           alt="User" class="img-fluid img-thumbnail rounded-circle border-0 mb-3"/>
      <h5 class="card-title">{{ user.name }}</h5>
      <p class="text-secondary mb-1">{{ user.jobTitle }}</p>
      <p class="text-secondary mb-1">{{ user.email }}</p>
      <p class="text-secondary mb-1">{{ user.phone }}</p>
    </div>
    <div class="float-right btn-group btn-group-sm">
    </div>
    <div class="card-footer" style="background-color: lightgray">
      <div style="margin-left: auto ;">
        <delete-button :user ="user"></delete-button>
        <edit-button @click="sendInfo()"></edit-button>

      </div>
    </div>
  </div>
</template>


<script>
import EditButton from "@/components/EditButton";
import DeleteButton from "@/components/DeleteButton";

export default {
  name: 'User',
  props: {
    user: Object
  },
  components: {
    EditButton,
    DeleteButton
  }, methods: {
    sendInfo(user) {
      this.selectedUser = user;
    }
  }
}

</script>

<style scoped>

.card-body {
  box-shadow: 0 0px 3px 0 rgba(0, 0, 0, .100), 0 1px 0px 0 rgba(0, 0, 0, .100);
}


.card {
  position: relative;
  display: flex;
  flex-direction: column;
  word-wrap: break-word;
  background-color: #fff;
  background-clip: border-box;
  border: 0 solid rgba(0, 0, 0, .125);
  border-radius: .25rem;
  margin-top: 6rem;
  height: 18rem;
}

.card-body {
  flex: 1 1 auto;
  min-height: 1px;
  border-radius: 0 0 .99rem .99rem;
}

.card-footer:last-child {
  border-radius: 0 0 .99rem .99rem;
}

.card-footer, .card-header {
  display: flex;
}

.card-footer {
  padding: .5rem 1rem;
  background-color: lightgray;
  border-top: none;
}
</style>
