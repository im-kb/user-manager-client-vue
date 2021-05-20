<template>
  <button class="btn btn-secondary tooltips" data-bs-target="#deleteModal" data-bs-toggle="modal"><i
      class="fa fa-times "></i></button>
  <delete-modal :user="user"></delete-modal>
</template>

<script>
import DeleteModal from "@/components/DeleteModal";

export default {
  name: "EditButton",
  components: {DeleteModal},
  props: {
    user: Object
  },
}
</script>
